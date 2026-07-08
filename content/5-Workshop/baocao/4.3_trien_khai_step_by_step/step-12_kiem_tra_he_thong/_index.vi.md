# Step 12: Kiểm Tra Hệ Thống 

---

### Health Check

```powershell
curl -s "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/health"
```

**Expected:**
```json
{"status":"ok"}
```

 *[CHÈN ẢNH: curl health check response]*

**Error Testing:**
```powershell
curl -s -X PUT "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/health"   # 405
curl -s "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/nonexistent"    # 404
```

---

### Kiểm Tra Frontend

Mở URL trong trình duyệt:
```
http://cloudnexusfrontendstack-<SUFFIX>.s3-website-ap-southeast-1.amazonaws.com
```

**Xác nhận:** React load đầy đủ, ReactFlow canvas hiển thị, dark mode.

 *[CHÈN ẢNH: Giao diện web trên browser]*
 *[CHÈN ẢNH: S3 bucket Properties → Static website hosting]*
 *[CHÈN ẢNH: View page source]*

---

### Generate Topology (AI)

```powershell
$body = '{"prompt":"simple web server with database"}'
[System.Text.Encoding]::UTF8.GetBytes($body) | Set-Content "$env:TEMP\req.json" -Encoding Byte -Force
curl -s -X POST "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/ai/generate" -H "Content-Type: application/json" --data-binary "@$env:TEMP\req.json"
```

**Khi quota còn:** Trả về JSON topology (nodes + edges)
**Khi quota hết:** `500` → CloudWatch log: `ClientError: 429 RESOURCE_EXHAUSTED`

 *[CHÈN ẢNH: curl 500 error]*
 *[CHÈN ẢNH: CloudWatch log 429]*
 *[CHÈN ẢNH: Lambda console + layer attached]*

---

### Validate Topology

```powershell
$body = '{"nodes":[{"id":"db","data":{"label":"DB","type":"database"}}],"edges":[]}'
curl -s -X POST "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/topology/validate" -H "Content-Type: application/json" -d $body
```

---

### Run Simulation

```powershell
$body = '{"topology":{"nodes":[{"id":"attacker","data":{"label":"Hacker","type":"attacker"}},{"id":"server","data":{"label":"Web","type":"server"}}],"edges":[{"source":"attacker","target":"server"}]},"scenario_name":"SQL Injection","target_node_id":"server","scenario_description":"Attacker tries SQL injection"}'
[System.Text.Encoding]::UTF8.GetBytes($body) | Set-Content "$env:TEMP\sim.json" -Encoding Byte -Force
curl -s -X POST "https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/api/simulation/run" -H "Content-Type: application/json" --data-binary "@$env:TEMP\sim.json"
```

---

### CloudWatch Logs

```powershell
aws logs describe-log-groups --log-group-name-prefix "/aws/lambda/CloudNexus"

$stream = aws logs describe-log-streams --log-group-name "/aws/lambda/CloudNexus-APIHandler" --order-by LastEventTime --descending --limit 1 --query "logStreams[0].logStreamName" --output text

aws logs get-log-events --log-group-name "/aws/lambda/CloudNexus-APIHandler" --log-stream-name "$stream" --limit 20 --query "events[].message" --output text
```

**Expected:**
```
INIT_START Runtime Version: python:3.12.mainlinev2.v11
START RequestId: xxx
END RequestId: xxx
REPORT RequestId: xxx  Duration: 61.09 ms  Billed Duration: 4048 ms  Memory Size: 512 MB  Max Memory Used: 193 MB  Init Duration: 3986.50 ms
```

| Metric | Giá trị | Ý nghĩa |
|--------|---------|---------|
| Init Duration | ~4000ms | Cold start |
| Duration | ~60ms | Xử lý request |
| Memory Size | 512 MB | Bộ nhớ cấp phát |
| Max Memory Used | ~193 MB | Bộ nhớ dùng thực tế |

 *[CHÈN ẢNH: CloudWatch Log stream]*
 *[CHÈN ẢNH: API Gateway console resources]*
 *[CHÈN ẢNH: Secrets Manager console]*

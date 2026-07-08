# Step 1: Cấu Hình AWS CLI 

---

### Thao tác

```powershell
aws configure
# AWS Access Key ID: ********
# AWS Secret Access Key: ********
# Default region name: ap-southeast-1
# Default output format: json

aws sts get-caller-identity
```

### Expected output

```json
{
  "UserId": "AIDA...",
  "Account": "<ACCOUNT_ID>",
  "Arn": "arn:aws:iam::<ACCOUNT_ID>:user/..."
}
```

 *[CHÈN ẢNH: Kết quả aws sts get-caller-identity hiển thị Account ID]*

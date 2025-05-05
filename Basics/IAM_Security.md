# IAM Security

- Root user can control/manage IAM users, billing, and the resources.
- Create a user from IAM in the console and allow it to access an S3 bucket.
- **ARN**: Any instance, user, or anything created as a resource in AWS has a unique ARN.

- Once the user is created and console access is given, we get the IAM username, password, and console sign-in URL.
  - This newly created IAM user `rudra-access-s3` will have no permissions to access S3 as it's not configured yet.
  - **Configuration step**: Go to IAM → Create Policy

### Standard Policy Format:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "allowsS3access",
      "Effect": "Allow",
      "Action": ["s3:*"],
      "Resource": ["*"]
    }
  ]
}
```

- Once the policy is created, go to IAM of the root user and attach the policy to the user. The IAM user should now be able to access the S3 bucket.

- **Creating a group and then creating a user under that group**: This allows attaching or granting permissions at the group level.

# Aws-cli Cheatsheet

### Create A New SES Access Key via IAM and Add Policy

Create a new user:
```
aws iam create-user --user-name ses-smtp-mail
```

Create a policy:
```
echo '{"Version": "2012-10-17", "Statement": [{"Effect": "Allow", "Action": ["SES:SendEmail", "SES:SendRawEmail", "SES:GetAccount", "SES:VerifyEmailIdentity", "SES:VerifyDomainIdentity", "SES:VerifyEmailAddress"], "Resource": "*"}]}' > sespolicy.json
```

Add policy to account:
```
aws iam put-user-policy --user-name ses-smtp-mail --policy-name NEW-SES-POLICY --policy-document file://sespolicy.json
```

Create an access and secret key:
```
aws iam create-access-key --user-name ses-smtp-mail
```

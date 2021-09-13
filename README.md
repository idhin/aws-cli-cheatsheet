# Aws-cli Cheatsheet

## Create a new SES Key via IAM:
```
aws iam create-user --user-name ses-smtp-mail
```
```
echo '{"Version": "2012-10-17", "Statement": [{"Effect": "Allow", "Action": ["SES:SendEmail", "SES:SendRawEmail", "SES:GetAccount", "SES:VerifyEmailIdentity", "SES:VerifyDomainIdentity", "SES:VerifyEmailAddress"], "Resource": "*"}]}' > sespolicy.json
```
```
aws iam put-user-policy --user-name ses-smtp-mail --policy-name NEW-SES-POLICY --policy-document file://sespolicy.json
```
```
aws iam create-access-key --user-name ses-smtp-mail
```

Answer the following:
What is needed to authorize your EC2 to retrieve secrets from the AWS Secret Manager?
  Set up an IAM Role to EC2 instance, IAM role attached to EC2 with permissions granted. EC2 instance can use AWS SDK to call GetSecretvalue on secrets manager API   and retriveve the secret values.
Derive the IAM policy (i.e. JSON)?
Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "secretsmanager:GetSecretValue",
            "Resource": "arn:aws:secretsmanager:us-west-2:123456789012:secret:prod/cart-service/credentials-*"
        }
    ]
}

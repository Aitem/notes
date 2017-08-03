
## Install

```
$ brew install awscli
```

## Login

```
# Login
aws configure

# Create profile
aws configure --profile <profile_name>
export AWS_DEFAULT_PROFILE=<profile_name>
export AWS_PROFILE=<profile_name>
```

## Public bucket

```
{
    "Version": "2008-10-17",
    "Statement": [
        {
            "Sid": "AllowPublicRead",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": [
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::<BUCKET_NAME>/*",
                "arn:aws:s3:::<BUCKET_NAME>"
            ]
        }
    ]
}

```



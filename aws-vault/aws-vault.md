## Setup

After installing `aws-vault` setup an aws profile using the following.
```
# Store AWS credentials for the "home" profile
$ aws-vault add user
Enter Access Key Id: ABDCDEFDASDASF
Enter Secret Key: %
```

A default region is needed when logging into the AWS console. Add the 
default region to your AWS config located `~/.aws/config`

```
[default]
region=us-east-1

[profile user]
...
```

## Assuming the role of another account

To assume the role of another account in AWS using `aws-vault` add the 
following to your aws config located `~/.aws/config`

```
[profile work]
source_profile=user
role_arn=arn:aws:iam::xxxxx:role/xxx
```

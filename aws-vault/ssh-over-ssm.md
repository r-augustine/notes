# How to ssh into EC2 instances using SSM

These instructions assume the following:
- EC2 instances uses an AMI with the `ssm agent` installed
- SSM role attached to the EC2 instances
- aws-vault configured to assume the appropriate role


## Install the AWS CLI

Instructions can be found [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)


## Install the Session Manager plugin for the AWS CLI

Instructions can be found [here](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)


## Setup SSH Proxy

Proxy ssh commands by adding the following to your ssh config located `~/.ssh/config`

```
# SSH over Session Manager
host i-* mi-*
    ProxyCommand sh -c "aws-vault exec wepala_prod -- aws ssm start-session --target %h --document-name AWS-StartSSHSession --parameters 'portNumber=%p'"
```

## Connect to EC2 Instance

Connection to the instance using the command `ssh -i private.key user@instance-id`

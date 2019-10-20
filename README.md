# EC2 Connect (in one command!)

## What is EC2 Instance Connect?

AWS recently introduced a new feature that allows you to inject keys into your instances with CLI calls.
The benefit of this is that you don't have to share keys anymore and the keys you use are only valid for 60 seconds.
You can read more about it [here](https://aws.amazon.com/blogs/compute/new-using-amazon-ec2-instance-connect-for-ssh-access-to-your-ec2-instances/)

## What does this script do?

This script will look up the instance id if you provide it an instance name,
or verify the instance id if you provide it an instance id.
It will then generate a new keypair, inject it into the instance and connect to it.

## How to use this script

Simply run `./ec2-connect <user>@<instance-id or name>` and the script will handle everything else.

There are also some more options for advanced users:

```text
$ ./ec2-connect --help
usage: ec2-connect [-h] [--region REGION] [--key-location KEY_LOCATION]
                   [--profile PROFILE] [-v]
                   instance

Connect to an EC2 instance with EC2 Connect installed

positional arguments:
  instance              The instance name or id and user, in the format
                        user@instance

optional arguments:
  -h, --help            show this help message and exit
  --region REGION, -r REGION
                        The AWS region the instance is in
  --key-location KEY_LOCATION, -k KEY_LOCATION
                        Location to store the generated keys
  --profile PROFILE, -p PROFILE
                        The AWS profile to use
  -v, --verbose         Increase output verbosity
```

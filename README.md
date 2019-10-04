# EC2 Connect (in one command!)

## What is EC2 Instance Connect?

AWS recently introduced a new feature that allows you to inject keys into your instances with CLI calls. The benefit of this is that you don't have to share keys anymore and the keys you use are only valid for 60 seconds. You can read more about it [here](https://aws.amazon.com/blogs/compute/new-using-amazon-ec2-instance-connect-for-ssh-access-to-your-ec2-instances/)

## What does this script do?

This script will look up the instance id if you provide it an instance name, or verify the instance id if you provide it an instance id. It will then generate a new keypair, inject it into the instance and connect to it.

## How to use this script

Simply run `./ec2-connect <instance-id or name> <user>` and the script will handle everything else.

Once you've run the script once it'll remember the user you use to connect so you only need to enter `./ec2-connect <instance-id or name>`

## Can I configure this script?

You sure can, start by configuring the variables at the top of the script. There are options there for where to save the keys, which region to use and which profile.

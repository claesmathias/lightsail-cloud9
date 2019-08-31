# lightsail-cloud9
Cloud9 is a complete web based IDE with terminal access, running on Lightsail.

## Create instance
Create AWS Lightsail instance via [AWS Lightsail CLI](https://docs.aws.amazon.com/cli/latest/reference/lightsail/index.html "AWS Lightsail CLI")
```
aws lightsail create-instances --instance-names "cloud9-vm" --availability-zone eu-west-2a --blueprint-id centos_7_1901_01 --bundle-id small_2_0 --user-data file://user-data.txt
```
You can find the script in `/var/lib/cloud/instance/user-data.txt` on the instance

## Configure instance
### Open ports
```
aws lightsail open-instance-public-ports --port-info fromPort=443,toPort=443,protocol=TCP --instance-name cloud9-vm
```

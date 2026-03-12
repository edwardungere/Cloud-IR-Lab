# Splunk setup

## SSH into instance

`chmod 400 "splunk-key.pem"` 

> Sets the key file to read-only for the owner, preventing reading, modification or deletion from other users

`ls -l /path/to/file`

> Check permissions of key file

`ssh -i /path/to/file username@<public IP of instance>`

> SSH into instance using .pem file (make sure instance is running)

`whoami`

> Verify user, should list "ec2-user"

## Setup splunk service

> Navigate to [Splunk Enterprise 10.2.1](https://www.splunk.com/en_us/download/splunk-enterprise.html?locale=en_us)

> Copy wget link and paste in shell for .rpm installation

### OR

`wget -O <splunk.rpm> "https://example.com/link/to/package"`

 > Run wget command with -O flag and optionally specify package name

`ls`

> Verify .rpm package is downloaded

### Installation 

`sudo rpm -i --prefix=/home/ec2-user/logging splunk.rpm`

> Install package using rpm and optionally specify location using prefix flag

`sudo /path/to/splunk/bin/splunk start --run-as-root`

> Run splunk

## Open Splunk
> Create a login for Splunk using username: admin and password:
> SPLUNK-$instance-id$


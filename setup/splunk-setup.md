# Splunk setup

## SSH into instance
1.  Sets the key file to read-only for the owner, preventing reading, modification or deletion from other users
 
 `chmod 400 "splunk-key.pem"`

2. Check permissions of key file

`ls -l /path/to/file`

3. SSH into instance using .pem file (make sure instance is running)

`ssh -i /path/to/file username@<0.0.0.0>`

4. Verify user, should list "ec2-user"

`whoami`

## Initial setup

1. Update list of available packages

`sudo dnf update`

2. Download and install packages

`sudo dnf upgrade`

3. Install wget tool

`sudo dnf install wget`

## Setup splunk service

1. Navigate to [Splunk Enterprise 10.2.1](https://www.splunk.com/en_us/download/splunk-enterprise.html?locale=en_us)

2. Copy wget link and paste in shell for .rpm installation

3. Verify .rpm package is downloaded

  `ls`

### Installation 

1. Install package using rpm
   
`sudo rpm -i <package-name.rpm>`

2. Verify splunk is installed

 `sudo ls /opt/splunk/bin/splunk`

3. Accept license agreements and start splunk

 `sudo -u splunk /opt/splunk/bin/splunk start --accept-license`

4. Create username and password credentials
   
6. Stop splunk service

 `sudo -u splunk /opt/splunk/bin/splunk stop`

6. Enable boot start with systemctl

 `sudo /opt/splunk/bin/splunk enable boot-start -systemd-managed 1 -user splunk`

7. Start Splunk daemon with systemctl

 `sudo systemctl start Splunkd`

8. Verify Splunkd status

 `sudo systemctl status Splunkd`


## Open Splunk

1. Open your browser and enter the instance's public IP address with port 8000 appended
 
`https://<0.0.0.0>:8000`

2. Login with the same previous credentials

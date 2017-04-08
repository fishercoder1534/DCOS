# DCOS
This is a notepad to document what I did to follow this [page](https://dcos.io/install/).

I chose [Basic Template](https://dcos.io/docs/1.9/administration/installing/cloud/aws/basic/).

Steps:
1. Log into your AWS console, select CloudFormation, select Template, specify S3 URL: https://s3.amazonaws.com/downloads.mesosphere.io/dcos/stable/cloudformation/single-master.cloudformation.json
2. Click Next, give it a name, leave all as default;
3. After your cluster stack spins up, click on the Outputs tab and copy/paste the Mesos Master hostname into your browser to open the DC/OS web interface.
Here's the screenshot when you access the Web UI:
https://ibb.co/jsZJT5
4. Installed DCOS cli: $cd && $curl -O https://downloads.dcos.io/binaries/cli/darwin/x86-64/dcos-1.9/dcos (for OS X)
5. $chmod +x dcos
6. $./dcos config set core.dcos_url 52.38.49.99 (THIS IS YOUR DCOS MASTER NODE IP)
7. $./dcos auth login
8. $./dcos config set core.ssl_verify False (either True or False)
9. $./dcos auth login
10. now you can happy dcos! try to run: $./dcos (you'll get the following output)

```
Steves-MacBook-Pro:~ stevesun$ ./dcos
Command line utility for the Mesosphere Datacenter Operating
System (DC/OS). The Mesosphere DC/OS is a distributed operating
system built around Apache Mesos. This utility provides tools
for easy management of a DC/OS installation.

Available DC/OS commands:

	auth           	Authenticate to DC/OS cluster
	config         	Manage the DC/OS configuration file
	experimental   	Manage commands that are under development
	help           	Display help information about DC/OS
	job            	Deploy and manage jobs in DC/OS
	marathon       	Deploy and manage applications to DC/OS
	node           	View DC/OS node information
	package        	Install and manage DC/OS software packages
	service        	Manage DC/OS services
	task           	Manage DC/OS tasks

Get detailed command description with 'dcos <command> --help'.
```
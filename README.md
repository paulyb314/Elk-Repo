# Elk-Repo
elk-project13
## Automated ELK Stack Deployment
#The files in this repository were used to configure the network depicted below.
**Note**: The following image link needs to be updated.  “NETWORK DIAGRAM FROM GLIPHY GOES HERE
![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)
#These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the file may be use># This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  # Machines Being Monitored
 # How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting unnecessary traffic to the network.
# Purpose of the load balancer and Jumpbox
My load balancer was deployed across all 4 virtual machines in my network. The load balancer distributes my traffic evenly across the network. This prevents my Jump-Box from being overloaded with tcp requests a>Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
Monitoring- Installed Beats
I installed on the Filebeat and the Metricbeat on my Elk Server.
The configuration details of each machine may be found below.
| Name                 | Function | IP Address | Operating System |   |
|----------------------|----------|------------|------------------|---|
| Jumpbox-Provisioner2 | Gateway  | 10.2.0.8   | Linux            |   |
| Elk-Server           | Ansible  | 10.0.0.4   | Linux            |   |
| Web-1                | User     | 10.2.0.5   | Linux            |   |
| Web-2                | User     | 10.0.0.6   | Linux            |   |
### Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Via ts80: The local host machine’s Ip 75.185.168.40 is whitelisted.
Machines within the network can only be accessed by the Jumbox via ssh through the ansible.
A summary of the access policies in place can be found in the table below.
11:44
| Name       | Publicly Accessible | Allowed IP Addresses |
|------------|---------------------|----------------------|
| Jump Box   | Yes                 | 10.2.0.8             |
| Elk-Server | No                  | 10.0.0.4             |
| Web-1      | No                  | 10.2.0.5             |
| Web-2      | No                  | 10.0.0.6             |
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because I was able to install dockers, protocols, and changes across my network effi>
Below is my playbook:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...
11:45
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
Path of docker PS output:
C:\Users\13309\OneDrive\Pictures\screenshot of elk docker.PNG
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
| Name       | Publicly Accessible | Allowed IP Addresses | Monitored? |
|------------|---------------------|----------------------|------------|
| Elk-Server | No                  | 10.0.0.4             |            |
| Web-1      | No                  | 10.2.0.5             | Yes        |
| Web-2      | No                  | 10.0.0.6             | Yes        |
I have installed the following Beats on these machines:
1)FileBeat
2) Metricbeat
These Beats allow us to collect the following information from each machine:
My Filebeat allows me to monitor all logs and provides a detailed report of all events. This gives me the ability respond to malicious activity in realtime.
Ex)
My Metricbeat analyses my data and pools my output to Logstash.
Ex)
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
________ Contains the playbook and copy the playbook to the roles directory.
Update the ansible.config file to include remote user access and the host file to include the monitored web servers ip addresses.
[Web Server]
Filebeat and metric beat need installed here
| Name       | Allowed IP Addresses | Installed |
|------------|----------------------|-----------|
| Web-1      | 10.2.0.5             | Yes       |
| Web-2      | 10.0.0.6             | Yes       |
[Elk]
| Name       | Allowed IP Addresses | Installed |
|------------|----------------------|-----------|
| Elk-Server | 10.0.0.4             | Yes       |
- _Which URL do you navigate to in order to check that the ELK server is running?
Navigate to http://< 52.251.52.47 >:5601/app/kibana to check that the installation worked as expected.
11:45
Commands needed to download playbook:
Ansible-playbook etc/ansible ansible-playbook

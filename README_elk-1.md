## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![project1 (1).jpg

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _playbook.yml____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: ._ playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure_____, in addition to restricting __access___ to the network.
- _the over all load: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _os logs____ and system _log files____.
- _TODO: What does Filebeat watch for?_ log files and log events
- _TODO: What does Metricbeat record?_ cpu and memory load

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| web1     | server   | 10.0.2.8   | linux            |
| web2     | server   | 10.0.2.9   | linux            |
| web3     | server   | 10.0.2.10  | linux            |
| ELK      | config   | 10.1.0.4   | linux            |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _jumpbox____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _ansible container the elk vm __.is only accessible through SSH and port 22 via the JumpBox VM and through port 5601 from the Host Machine.
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
| web1     |  no                 | 24.251.239.223                     |
| web2     |  no                 |                      |
  web3     |  no
Elk vm     |  yes
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
 configuration with Ansible include that all actions are carried out on the command line via SSH, it greatly simplifies configuration and set up because using Ansible allows administrators to ensure that the configuration of the infrastructure is identical where it needs to be, and it can be run from one machine and then pushed to thousands-- meaning that it is incredibly powerful in centralizing the management and set up of machines.

The playbook implements the following tasks:
-Install Containier
Install Docker
Install Python
Add Python script to Docker
Starts Docker
it Specifies the specific the amount of memory to be used
Download and start Elk container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-        web 1
         web 2
         web 3

We have installed the following Beats on these machines:
- file beat 
  metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing. 
collect metrics from the operating system and from services running on the server. Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat.yml file to etc/ansible/roles.
- Update the _filebeat.yml__ file to include elk server privite ip
- Run the playbook, and navigate to the kibania url to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ you copy the play book to the contanier
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which  machine to install the ELK server on versus which to install Filebeat on?_ you have to update that within the yml file its self
- _Which URL do you navigate to in order to check that the ELK server is running? kibana

_As a **Bonus**, 
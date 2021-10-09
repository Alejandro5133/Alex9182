## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/Alejandro5133/Alex9182/blob/main/Diagrams/Network_Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

elk-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    |  server  |  10.0.0.5  | Linux            |
| Web 2    |  server  |  10.0.0.6  | Linux            |
| Elk stack|  server  | 10.1.0.5   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
40.78.91.144

Machines within the network can only be accessed by the JumpBox.
184.103.171.190

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | Home Ip              |
| Web 1    | No                  | 52.160.69.237        |
| Web 2    | No                  | 52.160.69.237        |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The main advantage is the automation of the configuration.

The playbook implements the following tasks:

- docker.io
- Install pip3
- Install Docker python module
- Increase virtual memory
- download and launch a docker elk docker_container
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the yml file to control nob.
- Update the host file to includeips addresses on the network.
- Run the playbook, and navigate to http://[40.121.166.213]:5601/app/kibana to check that the installation worked as expected.

### Using the Playbook Pt.2
-Copy the multiple .yml files from Elkserver/Ansible to the jumpbox ansible continaer.

-Update the Hosts file to include two sections [elk] [webservers] with each having their respective VM IPs directly under them.

-Also in the Hosts file, update server IPs with Python3.

-Navigate to http://(ElkIPAddress):5601/app/kibana to make sure the elk server is running.

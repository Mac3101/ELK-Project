## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Update the path with the name of your diagram](Network diagram.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Beats file may be used to install only certain pieces of it, such as Filebeat.

Enter the playbook file._

This document contains the following details:
* Description of the Topology
* Access Policies
* ELK Configuration
o Beats in Use
o Machines Being Monitored
* How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly monitored, in addition to restricting traffic to the network.

What aspect of security do load balancers protect? By monitoring the operating status of the machine’s it is connected to in the network, Load balancers can distribute the traffic to machines accordingly. By doing this the load balancer will mitigate a DoS attack.  

What is the advantage of a jump box? The jump box acts as another layer of security. In this scenario the jump box is the only machine that is accessible to the internet. By restricting access to the jump box from the internet through controlled connection the network is not open to the internet. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the specific files or track specific information and system uptime.

What does Filebeat watch for? Enables analysts to monitor files for suspicious changes. 

What does Metricbeat record? Makes it easy to collect specific information about the machines in the network.

The configuration details of each machine may be found below.
Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name      | Function  | IP Address | Operating System      |
|-----------|-----------|------------|-----------------------| 
| Jump Box  | Gateway   | 10.0.0.5   | Linux (unbuntu 18.04) |
| Web 1     | Web Server| 10.0.0.8   | Linux (unbuntu 18.04) |
| Web 2     | Web Server| 10.0.0.9   | Linux (unbuntu 18.04) |
| Elk Server| ELK Stack | 10.1.0.4   | Linux (unbuntu 18.04) |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
64.92.54.88

Machines within the network can only be accessed by Jump Box.
Which machine did you allow to access your ELK VM? Jump Box 
What was its IP address? 104.44.142.217

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 104.44.142.217       |
| Web 1    | No                  | N/A                  |
| Web 2    | No                  | N/A                  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

What is the main advantage of automating configuration with Ansible? Ansibles has extensive documentation on how to accomplish nearly everything. Ansible has a module that will accomplish what we need to have done, thus saving time writing scripts and correcting errors with our script. 

The playbook implements the following tasks:
 In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
* Playbook Module installation (instructions for installation of playbook)
o Use Apt modules,
* Install docker.io,
* Install python3-pip,
o Use pip module,
* Install Docker module,
* Play Book Memory Utilization Modules (instructions for creating and expanding memory usages)
o Use command module,
* Increase virtual memory,
o Use sysctl module,
* Use more memory,
* Playbook Execution Modules (instructions for launching and running playbook)
o Use Docker container module,
* Download and launch a docker elk container,
o Use sysmtemd
* Enable service docker on boot, 
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
List the IP addresses of the machines you are monitoring;
10.0.0.8 and 10.0.0.9

We have installed the following Beats on these machines:
Specify which Beats you successfully installed; Filebeats, Metric Beats Web-1 and Web-2.

These Beats allow us to collect the following information from each machine:
In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
Copy the Metricbeat.deb file to ansible playbook.
Update the metricbeat config file to include...
Run the playbook, and navigate to 13.66.189.169 to check that the installation worked as expected.



Answer the following questions to fill in the blanks:

Which file is the playbook? Metricbeat-playbook.yml. 
Where do you copy it? Artifacts.elastic.co

Which file do you update to make Ansible run the playbook on a specific machine? /etc/ansible/hosts

How do I specify which machine to install the ELK server on versus which to install Filebeat on? IP Address

Which URL do you navigate to in order to check that the ELK server is running? https:13.66.189.169:5601/app/kibana#/home.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

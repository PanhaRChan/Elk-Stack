## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[Images/ELK-STACK-PROJECT.drawio.png](https://github.com/jvicious126/Elk-Stack-/blob/fa48380fcd283f5852e5e17531acb8569f39d781/Images/ELK-STACK-PROJECT.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - Playbooks/install-elk.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant, in addition to restricting traffic to the network.
- The Load Balancer adds an additional layers of security from emerging threats such as DDoS attacks. It also authenticates users for access. In addition to the added layer of security provided by the Load Balancer, the Jump Box acts as a "bridge" between two trusted networks and is treated as a single entryway to a server group.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat: Watches and records log files from locations specified and forwards them to Logstash for indexing.
- Metricbeat: Is used to monitor and collect data such as system CPU and memory to load in a docker environment.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name      | Function | IP Address | Operating System |
|-----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web-1     | WebVM    | 10.0.0.7   | Linux            |
| Web-2     | WebVM    | 10.0.0.6   | Linux            |
| Web-3     | WebVM    | 10.0.0.9   | Linux            |
| ELK-Server| ELK-Stack| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by the JumpBox Provisioner.
- The JumpBox-Provisioner is the only machine I allowed access to the ELK Server. I used the private IP of the JumpBox-Provisioner to access the machines in the network

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 154.6.26.7           |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows us to simplify complex tasks thus freeing up time and increases efficiency.


The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 10.0.0.7
- Web-2 10.0.0.6
- Web-3 10.0.0.9

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the hosts file to include the ip addresses 
- Run the playbook, and navigate to Kibana using the ELK-Server public IP specifying port '5601' to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- Next we will update the hosts to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- Then we will navigate to the ELK-Server machines public IP and specify port '5601' in order to check that the ELK server is running.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

# Elk-Project
Elk-Project

Cloud Network Creation

The files in this repository were used to configure the network below

These files have been tested and used to generate a live ELK deployment on
Azure. They can be used to either recreate the entire deployment pictured above or can be run individually. For instance, you are able to go into the files directory, located in the /etc/ansilbe and run $

This document contains the following details:
-Description of the Topologyc
-Access Policies
-ELK Configuration
-beats in use
-machines being monitored
-how to use the Ansible Build


## Description of the Topology

The main purpose of this network is to expose a load-balance and monitiored instance of DVWA, the vulnerable web application.

load balancing ensures that the application will be highly protected, in addition to restriction traffic to the network.
-what aspect of security do load balancers protect? Load balancers protect servers from being overloaded. If one server goes out, traffic can be redistributed.

- what is the advanted of a jump box? The jump box secures access to administrative tasks.

Integrating an ELK server allows users to easliy monitor the vulnerable VMs for changes to the logs and system traffic.

- What does filebeat watch for? Filebeat watches and monitors the log files and locations which users specify and records.

- What does metricbeat record? Metricbeat records the datea on the operating system and applications.

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System     |
|----------|----------|------------|----------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux (ubuntu 18.04) |
| Web-1    | Server   | 10.0.0.7   | Linux (ubuntu 18.04) |
| Web-2    | Server   | 10.0.0.6   | Linux (ubuntu 18.04) |
| ElkMach  | Monitors | 10.1.0.4   | Linux (ubuntu 18.04) |


## Access Policies

The machines on the internal network are not exposed to the public internet.

Only the JumpBox Provisioner machine can accept connections from the internet. Access to this machine  is only allowed from the follow IP addresses:
-IP: my personal IP


Machines within the network can only be accessed by JumpBox Provisioner.
-Which machine did you allow to access your ELK VM? Only the JumpBox Provisioner has access to the ELK vm. IP is 10.1.0.4

A summary of the access policies in place can be found in the table below.

The machines on the internal network are not exposed to the public internet.

Only the JumpBox Provisioner machine can accept connections from the internet. Access to this machine  is only allowed from the follow IP addresses:
-IP: my personal IP


Machines within the network can only be accessed by JumpBox Provisioner.
-Which machine did you allow to access your ELK VM? Only the JumpBox Provisioner has access to the ELK vm. IP is 10.1.0.4

A summary of the access policies in place can be found in the table below.


| Name        | Publicly Accessilbe | Allowed IP Addresses |
| ------------|---------------------|----------------------|
| JumpBox     | Yes                 | my personal IP       |
| Web-1       | No                  | 10.0.0.4             |
| Web-2       | No                  | 10.0.0.4             |
| ElkMach     | No                  | 10.0.0.4             |


## Elk Configuration


Ansilbe was used to autonate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it seals it from vulnerabilities.
- A main advantage of automating with Ansible.


The playbook implements the following tasks:
-install docker.io
-install pip3
-install docker python module
-increase the virtual memory
-download and launch the docker


## Target Machines & Beats

This Elk server is configures to monitor the following machines:
-Web-1 10.0.0.6
-Web-2 10.0.0.7
We have installed the following Beats on these machines:

-Filebeat and metricbeat

These beats allow us to collect the following information from each machine:
-The beats allow us to collect date about log events and users as well as collect statics and metrics on ours

## Using the Playbook

In order to use the playbook, you will need to have an Ansilbe control node already confirgured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
-copy the playbook file ansilbe.
-update the host file to include webserver and ELK.
-run the playbook, and navigate to kibana to check that the installation worked as expected.

These commands are what the user will need to run to download the playbook, update the files, and run the playbook.

# Honeypot

HONEYPOT

Objective
The objective of this project was to gain exposure to a common cybersecurity defense mechanism known as a honeypot used to lure and trap attackers. 

Tools Used
- T-Pot
- Vultr Cloud Server
- Kibana
- Ubuntu

Spin up a VM server in the cloud, VULTR had a bonus sign on credit so we went with that cloud provider

I chose Ubuntu as my OS out of preference

We also chose 160 GB of SSD and 8 GB of RAM to meet the minimum specs required of our honeypot platform

![VM](https://github.com/user-attachments/assets/3c9df45d-f608-4e9a-9732-0cd399bcb547)

Configuring the virtual server we have opened up traffic to all possible port numbers ranging from [0-65,535] but making the ports inaccessible so that the server will be visible but inaccessible

![firewall](https://github.com/user-attachments/assets/a66d3360-b00f-4efb-b16c-a96f7f77d50d)

To install our honeypot platform t-pot we must download from outside the root account, so we will make a user with admin privileges

sudo adduser <adrian>

sudo usermod -aG sudo <adrian>

We need to install curl to pull T-Pot from the repository in Github

Sudo apt install curl 

Then we run the installer cmd provided for us in the T-Pot documentation ”env bash -c "$(curl -sL https://github.com/telekom-security/tpotce/raw/master/install.sh)"

![Screenshot 2025-03-23 162147](https://github.com/user-attachments/assets/d0a80bd2-ce58-4930-a7e5-537eb18797fc)

After installing the honeypot we are ready to access the dashboard

Upon reading the documentation I found that the teapot is accessible for management via ports 64294,64296,64297.

I want the web based gui so I will remote into the NGINX reverse proxy https on port 64297. 

I open up these ports to my machine by navigating to the "Source" tab and select the "My IP" option so we will be able to access the machine from our current IP.

![documentation](https://github.com/user-attachments/assets/a417aa16-de5b-41dc-9c79-25c2c8f5ec99)

We will search the link below to access the web gui
https://45.32.215.92:64297/

In the T-pot dashboard we have shortcuts to a few different tools
Attack Map:

Cyberchef: An excellent tool for encoding and decoding data

Spiderfoot: An OSINT tool that can be used for reconnaissance 

Elasticvue: A tool allowing you to search, filter and query through data clusters

Kibana: A tool that can display a customized dashboard for log analytics

Both Elasticvue and Kibana are tools that comprise the SIEM known as “ELK stack” the only tool missing that would complete the ELK Stack is Logstash.

<img width="953" alt="image" src="https://github.com/user-attachments/assets/c72e4071-2638-438d-93a1-a5f378aa0871"/>

If we open up the Attack Map, we can see tracers of real time connection attempts including the geolocation and the port of the attempted attack on our machine.

<img width="886" alt="image" src="https://github.com/user-attachments/assets/82a8391e-8ad5-4729-8b24-39d4c1aa281e" />


To see the T-Pot dashboard, I will open Kibana and select the dashboard created for our platform

![Screenshot 2025-03-25 195144](https://github.com/user-attachments/assets/68a9c6e3-22ac-4cd6-8b01-994970c8caa3)

From this dashboard we can see several visualizations that account for attacks by country, which port they attempted to connect to, the OS the attacker was using, and the usernames and passwords that were attempted.

Every screenshot should have some text explaining what the screenshot is about.

Example below.

Ref 1: Network Diagram

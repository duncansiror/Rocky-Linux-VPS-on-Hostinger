# Initial VPS Setup

Before we get started on the more technical aspects of Linux and a virtual private server, we must first purchase resources from a web hosting company. Fortunately, Hostinger makes the process quite seamless. 

## Domain Purchase

Start buy purchasing an available domain name. Luckily, I have a unique name. 

<img width="1408" height="584" alt="domainpurchase" src="https://github.com/user-attachments/assets/e2fb6054-0433-47a2-852a-a94ab77b942d" />

## Select Operating System

I chose Rockly Linux because of its compatibility with RHEL and abundance of community support.

<img width="586" height="413" alt="rockyselection" src="https://github.com/user-attachments/assets/552bd415-4d21-4ef6-a3b7-5663750f27fe" />

### Additional Features

A malware scanner is invaluable for security purposes (also helps that it's free). This will be especially useful later for vulnerablity testing. Containers are a crucial component of modern infrastructure, so I'll include Docker nmanager as well. 

<img width="1200" height="345" alt="features" src="https://github.com/user-attachments/assets/b9418eb7-36de-47cc-8a00-82d7c011bd84" />

### Select Plan

I chose a VPS plan with the following specifications. Hostinger has four plans to choose from. This was the most popular, but feel free to choose what feels right for you. 

<img width="287" height="859" alt="kvm2selection" src="https://github.com/user-attachments/assets/a104a386-07d2-4ab4-b384-9e2072f8478f" />

### Create Root Password

Of course, one must create a password for the root account.  I will go over SSH keys in a separate tutorial. 

<img width="1171" height="375" alt="pw" src="https://github.com/user-attachments/assets/f4a91ca4-caea-40f5-a24e-66a3de9bffab" />

## Server Overview

After initial setup has been completed and the server has been running for several minutes, I can now see an overview which includes operating system, hostname, IPv4 addresse, plan details and resource consumption.

<img width="1142" height="865" alt="overview" src="https://github.com/user-attachments/assets/271189bb-a68a-40ae-8f90-93fe69e914ff" /><br/>

That concludes the first tutorial for setting up a VPS. In the following guides, I'll explain SSH and DNS. 

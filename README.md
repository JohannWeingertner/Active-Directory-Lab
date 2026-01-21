<img width="2500" height="415" alt="image" src="https://github.com/user-attachments/assets/b59c5e80-a6a6-4f13-92e4-6902f5da6eb2" />

This lab was developed through independent research and self-directed learning, deliberately avoiding step-by-step Active Directory tutorial videos. I maintained a minimal reliance on YouTube content

---
# Microsoft Active Directory Lab

## Lab Overview
The overall goal of this lab is to create a permanent Active Directory environment on my Proxmox nodes. I want to use this AD network for:

  -**Penetration Testing Practice** - Simulating real-world attacks and defenses, while also configuring to protect against these attacks.

  -**Splunk Log Analysis** - Generating security logs for practicing investigations in Splunk

  -**Hands-on Learning** - Gaining experience in AD like, setting up and configuring an Active Directory network, managing AD infrastructure, understanding AD security and administration.

  -**Communication with an AWS Instance** - Gaining practical hands on learning for studying for AWS SAA certifcation.

## Lab Objectives

The primary objective is to deploy an Active Directory network on another etwork segment within my Proxmox environment. This design serves two key purposes:

1. **Security Isolation** - Utilize an OPNsense router to enforce strict traffic control, enabling me to:
   - Selectively block or permit traffic between networks whenever I want.
   - Safely conduct penetration testing exercises in a controlled environment
   - Isolate lab activities from my primary network whenever I deem fit

2. **Networking Practice** - Apply and expand my networking knowledge by:
   - Configuring inter-network routing
   - Implementing firewall rules and network policies
   - Managing segmented network infrastructure

And to also:

- Build a realistic Active Directory domain on an isolated network segment
- Deploy member servers with enterprise roles and applications
- Set up client workstations for end-user simulation

## The Guard.net Network

<img width="1543" height="800" alt="Network Chart (1)" src="https://github.com/user-attachments/assets/5a020b4e-8593-43c9-bd07-1b49994711f3" />

<img width="298" height="258" alt="Screenshot 2026-01-20 at 10 55 59 PM" src="https://github.com/user-attachments/assets/6d5a5a0b-84ff-4d97-a101-a7c6e25aa1e2" />

The steps to actually creating an internal Virtual network on a another network inside a proxox thats on another network was actually quite fun to solve and figure out.

I first had to create a bridge on Proxmox Node Orisis (Because I did want this network to communicate to the internet through my main Opnsense Router and to allow me to communicate with it.)

<img width="1035" height="123" alt="Screenshot 2026-01-20 at 10 56 40 PM" src="https://github.com/user-attachments/assets/43123980-4906-46a9-b1c4-c6847ed4dab8" />

After creating this linux bridge, I think create a Opnsense VM using proxmox helper scripts (https://community-scripts.github.io/ProxmoxVE/scripts?id=opnsense-vm), which enabled rapid provisioning of a pre-configured OPNsense VM.

I then configured and assigned the correct ip addresses for communication between the networks. (I spend an hour trying to figure why it wasnt working, I figured out the Virtual interfaces were flip flopped, so I reassigned the correct Virtual interfaces to the VM).

<img width="435" height="185" alt="Screenshot 2026-01-20 at 11 01 57 PM" src="https://github.com/user-attachments/assets/11bb182c-295a-415e-8061-7a4a69e6b295" />



## Attribations:
Wireless router icons created by Nueng_wana
Computer icons created by Hilmy Abiyyu A.



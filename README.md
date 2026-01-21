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

The next step for me was to create a windows server VM. I chose windows 2022. To setup a vm of any windows vm on proxmox, is to download virtio drivers for windows from Redhat, and to install the actual windows iso image with the virtio drivers.

After pprovision the windows server, I then started configuring the windows server to becoming a Domain Controller.

<img width="735" height="550" alt="Screenshot 2026-01-20 at 9 25 13 PM" src="https://github.com/user-attachments/assets/b9d28c23-1a43-40a8-a517-036d27bbab6e" />

<img width="547" height="401" alt="Screenshot 2026-01-20 at 9 31 07 PM" src="https://github.com/user-attachments/assets/39fc5aa4-91b1-4368-9d33-f59529fa521c" />

And then after rebooting we can see the changes.

<img width="733" height="539" alt="Screenshot 2026-01-20 at 11 11 45 PM" src="https://github.com/user-attachments/assets/f4dd81be-7eaf-4199-a95c-0607ea9cc38b" />

<img width="712" height="464" alt="Screenshot 2026-01-20 at 11 11 30 PM" src="https://github.com/user-attachments/assets/b6ac0762-6b05-4db0-bd34-4e94ad02523c" />

I chose lab.guard.net since my 10.0.0.0/24 network uses guard.net.

Then the next step is to actually get a pc to join this domain controller. I proceeded to provision and configure the windows 10 pc.
<img width="323" height="449" alt="Screenshot 2026-01-20 at 11 19 09 PM" src="https://github.com/user-attachments/assets/72da5430-68b6-4b86-9c5d-6e6eed5ddc8a" />

<img width="446" height="355" alt="Screenshot 2026-01-20 at 11 23 33 PM" src="https://github.com/user-attachments/assets/6a5e9c9b-d3b2-45b4-b7c0-eeebb69aae72" />

<img width="453" height="360" alt="Screenshot 2026-01-20 at 11 39 20 PM" src="https://github.com/user-attachments/assets/85041057-5ac4-4a14-8388-19319b2bfd63" />

<img width="456" height="357" alt="Screenshot 2026-01-20 at 11 40 35 PM" src="https://github.com/user-attachments/assets/33da51b2-f5d6-4582-9f0c-2fcf730fc444" />

<img width="326" height="170" alt="Screenshot 2026-01-20 at 11 40 59 PM" src="https://github.com/user-attachments/assets/21a8e5ed-bb31-4a57-a956-0b498869365f" />

<img width="457" height="364" alt="Screenshot 2026-01-20 at 11 41 38 PM" src="https://github.com/user-attachments/assets/de64ef72-99e5-4ebb-a982-567d6c267533" />

I had an issue with logging in because I didn't set the DNS settings of this to the Domain Controller, so I had to do that before any of this.










## Attribations:
Wireless router icons created by Nueng_wana
Computer icons created by Hilmy Abiyyu A.



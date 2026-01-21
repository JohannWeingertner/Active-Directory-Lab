<img width="2500" height="415" alt="image" src="https://github.com/user-attachments/assets/b59c5e80-a6a6-4f13-92e4-6902f5da6eb2" />

This lab was developed through independent research and self-directed learning, deliberately avoiding step-by-step Active Directory tutorial videos. I maintained a minimal reliance on YouTube content

---
# Microsoft Active Directory Lab

## Lab Overview
The overall goal of this lab is to create a permanent Active Directory environment on my Proxmox nodes. I want to use this AD network for:

  -**Penetration Testing Practice** - Simulating real-world attacks and defenses, while also configuring to protect against these attacks.

  -**Splunk Log Analysis** - Generating security logs for practicing investigations in Splunk

  -**Hands-on Learning** - Gaining experience in AD like, setting up and configuring an Active Directory network, managing AD infrastructure, understanding AD security and administration.

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


<img width="1636" height="1341" alt="Network Chart" src="https://github.com/user-attachments/assets/cf34f40a-5a8f-43ca-83e3-97e551601f5d" />

The steps to actually creating an internal Virtual network on a another network inside a proxox thats on another network was actually quite to solve and figure out.

## Attribations:
Wireless router icons created by Nueng_wana
Computer icons created by Hilmy Abiyyu A.



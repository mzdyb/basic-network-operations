# Automating basic network operations with Ansible
This repo shows the simple example of network automation using [Ansible validated content](https://www.redhat.com/en/blog/automate-expert-ansible-validated-content).
The following use cases are presented:
1. Create backup
2. Create inventory (SoT) for brownfield network
3. Detect configuration drift
4. Remediate configuration drift

Ansible collection _network.backup_ is used to create backup . For other three use cases _network.base_ collection is used.
It this case both backup and inventory are copied to external server (backup host) but another use case might be to copy them to Version Control system like GitHub or GitLab.
The folder structure with files created on backup host looks like this:  
![image](https://github.com/user-attachments/assets/f2a6a811-055f-46f4-a3b4-5eee9e15b09a)  

The _network_backup_ folder stores automatically created network configuration backup and _host_vars_ folder stores a subset of network configuration data which we can use as Source of True for network configuration. In general SoT is a central repository for configurations with up to date and reliable information. It serves as the reference point for desired state of the infrastructure. If we introduce this concept to our network management then we should have a way to automatically detect configuration drift between our SoT (reference configuration) and configuration on networking devices. This is the purpose of "Detect configuration drift" use case. When drift is detected we can fix it using "Remediate configuration drift" use case.

## Ansible Automation Platform workflows
Two automation workflows are created:
1. Create backup and create inventory (SoT) for brownfield network
![image](https://github.com/user-attachments/assets/e077f311-828e-4ab6-882c-ce66f09ded69)
This workflow creates network configuration backup and inventory with network data.

3. Detect and remediate configuration drift:
![image](https://github.com/user-attachments/assets/34518168-dbd9-411c-b1d1-3eabca8cbafa)
This workflow detects configuration drift and waits for approval before remediating it.

## Network topology
Ansible validated content collections for networking are vendor agnostic but in this case Cisco infrastructure is used:  
![image](https://github.com/user-attachments/assets/948636b6-ec33-4a80-ab10-a06a2f7a82ed)

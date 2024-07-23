# Automating basic network operations with Ansible
This repo shows simple examples of network automation using [Ansible validated content](https://www.redhat.com/en/blog/automate-expert-ansible-validated-content).
The following use cases are presented:
1. Create backup
2. Create inventory (SoT) for brownfield network
3. Detect configuration drift
4. Remediate configuration drift

Ansible collection _network.backup_ is used to create backup . For other three use cases _network.base_ collection is used.
It this case both backup and inventory are copied to external server (backup-host) but another use case might be to copy them to Version Control system like GitHub or GitLab.
The folder structure with files created on backup-host looks like this:  
![image](https://github.com/user-attachments/assets/f2a6a811-055f-46f4-a3b4-5eee9e15b09a)  

The network_backup folder stores automatically created network configuration backup and host_vars folder stores network configuration data which we can use as Source of True for network configuration. SoT is central repository for configurations with up to date and reliable information. It serves as the reference point for desired state of the infrastructure. If we introduce this concept to our network management then we should have a way to automatically detect configuration drift between our SoT (reference configuration) and configuration on networking devices. This is the purpose of "Detect configuration drift" use case. When drift is detected we can fix it using automation presented in "Remediate configuration drift" use case.

## Ansible Automation Platform workflows
Two automation workflows are created for our use cases:
1. Create backup and create inventory (SoT) for brownfield network
![image](https://github.com/user-attachments/assets/e077f311-828e-4ab6-882c-ce66f09ded69)

2. Detect and remediate configuration drift:
![image](https://github.com/user-attachments/assets/34518168-dbd9-411c-b1d1-3eabca8cbafa)

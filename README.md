# Automating basic network operations with Ansible
This repo shows simple examples of network automation using [Ansible validated content](https://www.redhat.com/en/blog/automate-expert-ansible-validated-content)
The following use cases are presented:
1. Create backup
2. Create inventory (SoT) for brownfield network
3. Detect configuration drift
4. Remediate configuration drift

Ansible collection network.backup is used to create backup . For other three use cases network.base collection is used.
It this case both backup and inventory are copied to external server (backup-host) but another use case might be to copy them to Version Control system like GitHub or GitLab.



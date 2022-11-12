# awx-deploy-server
For deploying servers via AWX and VMware vCenter

# Prerequisites 
To get started with this repo, you'll need the following:
 - An AWX instance -> [Ansible AWX Repo](https://github.com/ansible/awx)
 - A git repo (fork of this)
 - VMware vCenter Server 
 - VMware template for a VM (Ubuntu 22.04 LTS in this case)

# Getting Started
## In AWX
1) Create source control and VMware vCenter Credentials, make sure to use their respective credential types too
2) Create a project and point to your fork and branch in Github, GitLab, etc. Make sure to check the box to update on launch. This is pull the latest commit into AWX
3) Create an inventory and only enter `localhost`. Since we are building VMs, we don't need to have servers outside of our AWX instance. 
4) Create a Template and choose **Job Type** of `run` then select for inventory and project from the dropdowns. Set your playbook as well. You can set your execution environment if you want, but it shouldn't be required. 
5) In the template, set your credentials to the vCenter ones you made eariler.
6) Under **Variables**, you can enter the following variables, but most likely you will need to customize these to your environment
    - cluster_name
    - folder_path
    - vm_name
    - datastore_name
    - datacenter_name
    - network_name
    - template
    - guest_domain
    - guest_dns_server1
    - guest_dns_server2
    - guest_domain_name1
    - guest_domain_name2
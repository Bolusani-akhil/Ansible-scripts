# Ansible-scripts


Basically we will have ansible server and target servers.
 
 step 1: Create the servers in AWS EC2
 
 step 2: connect to the servers by ssh [Example: ssh -i ""C:\Users\DELL\Downloads\target.pem"" ubuntu@98.93.139.174]
 
 step 3: Install ansible in ansible server  
 
 step 4: Enable password less authentication between target and ansible server using ssh-keygen command

**Commands**

Ansible adhoc command for single executing single task/instruction

Below command is used to create a file named devopsclass in target servers mentioned in inventory file 

    ansible -i inventory all -m "shell" -a "touch devopsclass"


Ansible playbook is used for executing multiple instructions

Inventory file (grouping servers using syntax [$server_type] )

The below command will install and start nginx in target servers

    ansible -i inventory first-playbook.yml

If we use -vvv[Verbose] in ansible playbook command we can see the logs for debugging

    ansible -vvv -i inventory first-playbook.yml

**Ansible Roles**

Roles are used to write complex ansible playbooks. It will make the process easier

For example if we want to configure k8s cluster where it has following tasks

Create 3 EC2 instances in AWS

1 EC2 for master node

2 EC2's for worker nodes

It need lot of other tasks like secrets, configmaps etc,.

So writing playbook is difficult for that we will got for roles.

By executing following command it will create a folder structure where it will contain sub folders named templates,files,tasks,meta,handlers,tests,vars,defaults and readme file

Command: 

    ansible-galaxy role init kubernetes

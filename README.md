# Ansible-scripts
Ansible scripts

# Basically we will have ansible server and target servers.
# step 1: Create the servers in AWS EC2
# step 2: connect to the servers by ssh [Example: ssh -i ""C:\Users\DELL\Downloads\target.pem"" ubuntu@98.93.139.174]
# step 3: Install ansible in ansible server  
# step 4: Enable password less authentication between target and ansible server using ssh-keygen command
# Commands
# Ansible adhoc command for single executing single task/instruction
# Below command is used to create a file named devopsclass in target servers mentioned in inventory file 
ansible -i inventory all -m "shell" -a "touch devopsclass"


# Ansible playbook is used for executing multiple instructions
#  Inventory file (grouping servers using syntax [$server_type] )
# The below command will install and start nginx in target servers
ansible -i inventory first-playbook.yml

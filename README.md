Follow the below steps to deploy the ToDo app:

DEPLOYMENT STEPS:

2. Change directory to user home directory
	- cd /home/<user>
 
3. Create a directory to store Ansible playbooks and change directory to it
	- mkdir ansible_playbooks
    - cd ansible_playbooks
 
4. Create a YAML file for the ANsible playbook content
    - touch todo_install.yml
 
5. Copy the Ansible playbook content in it
    
6. Make the file executable
    - chmod 755 todo_install.yml

7. Execute the Ansible playbook to deploy the Kubernetes cluster:
    - ansible-playbook -i hosts todo_install.yml
  

IMPORTANT !

After a VM reboot, it is possible that Kubernetes cluster to be no longer available, reporting the following error: ”The connection to the server :6443 was refused - did you specify the right host or port?”

In order to fix it, run the following commands, starting as kubernetes admin user:

    - sudo -i
    - swapoff -a
    - exit
	  - strace -eopenat kubectl version
   
To check if the Kubernetes cluster is now available, run "kubectl get nodes".

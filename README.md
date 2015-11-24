#Ansible 是什么(what it is)

>####Ansible: ansible is an IT automation tool. It can configure systems, deploy software, and orchestrate more advanced IT tasks such as continuous deployments or zero downtime rolling updates.  
####If needed, Ansible can easily connect with Kerberos, LDAP, and other centralized authentication management systems.  
--[http://docs.ansible.com/ansible/index.html](http://docs.ansible.com/ansible/index.html)

#Ansible 怎么安装(how to install)

 - Mac OS
 
 ```bash
 	$ berw install ansible
 ```
 - Centos 
 
 ```bash
 	$ rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
 	$ sudo yum install ansible
 ```
 
#Ansible 怎么使用(how to use)
 - helloworld (**key:**  inventory, module, host, group)

 ```bash
   	$ ansible -i host node01 -m shell -a "echo helloworld"
   	$ ansible -i host node01 -m shell -a "uname -a"
 ```
**Module:** `shell`, `copy`, `file`, `get_url`, `unarchive`, `yum`, `template`...
 - install sl (**key:** tasks,playbook)
 
 ```bash
   	$ ansible -i host node01 -m yum -a "name=sl state=present|latest|absent"
 ```
 ```bash
   	$ ansible-playbook -i host v1.yml
 ```
 >Playbooks are Ansible’s configuration, deployment, and orchestration language. They can  describe a policy you want your remote systems to enforce, or a set of steps in a general IT process.
If Ansible modules are the tools in your workshop, playbooks are your design plans.
 
 - copy youself.txt to remote_host (**key:** role, extra-vars) 
 
 ```bash
   	$ ansible-playbook -i host v2.yml --extra-vars "dest=hg_repository"
 ```
 
#Ansible 还能做什么(what can be done)
 - ansible-galaxy
 - ansible-vault
# What is Ansible


>#### Ansible is an IT automation tool. It can configure systems, deploy software, and orchestrate more advanced IT tasks such as continuous deployments or zero downtime rolling updates.  
  
[http://docs.ansible.com/ansible/index.html](http://docs.ansible.com/ansible/index.html)

# Why Ansible
  - Lots of module
  
  [http://docs.ansible.com/ansible/list_of_all_modules.html](http://docs.ansible.com/ansible/list_of_all_modules.html)

  - Batch processing 

  - Based YAML syntax


# How to install Ansible

 - Mac OS
 
 ```bash
 	 $ berw install ansible
 ```
 - Centos 
 
 ```bash
 	 $ rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
   $ sudo yum install ansible
 ```
 
 - Other System 
 
   [https://www.google.co.in/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=how%20to%20install%20ansible](https://www.google.co.in/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=how%20to%20install%20ansible)

 
# How to use Ansible
 - helloworld (**key:**  inventory, module, host, group)

 ```bash
  $ ansible -i hosts node01 -m shell -a "echo helloworld"

  $ ansible -i hosts node01 -m shell -a "uname -a"
 ```
**Module:** `shell`, `copy`, `file`, `get_url`, `unarchive`, `yum`...
[http://docs.ansible.com/ansible/list_of_all_modules.html](http://docs.ansible.com/ansible/list_of_all_modules.html)
 - install sl (**key:** tasks,playbook)
 
 ```bash
   	$ ansible -i hosts node01 -m yum -a "name=sl state=present|latest|absent" --sudo
 ```
 ```bash
   	$ ansible-playbook -i hosts v1.yml
 ```
 >Playbooks are Ansible’s configuration, deployment, and orchestration language. They can  describe a policy you want your remote systems to enforce, or a set of steps in a general IT process.
If Ansible modules are the tools in your workshop, playbooks are your design plans.
 
 - deploy webApp to remote_host (**key:** role) 
 
 ```bash
   	$ ansible-playbook -i hosts v2.yml
 ```
 
# What else can Ansible do
 - ansible-galaxy
 - ansible-vault




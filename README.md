# http-ansible

Version 2 - > Ansible & HA Proxy configured using Vagrant
•	1 x Ubuntu Vagrant VM running Ansible
•	1 x Ubuntu Vagrant VM running HA Proxy configured via Ansible
•	2 x Ubuntu Vagrant VM running apache2 configured via Ansible
How to Deploy
1.	Download & Install Vagrant https://www.vagrantup.com/downloads.html 
2.	Download my vagrantfile from github (source below)
3.	Run the following commands
a.	Vagrant up **boxname** 
4.	Configure a static or dynamic ip on each box
5.	Install Ansible on the Ansible Vagrant VM (could bootstrap this from vagrant, but pretty pointless considering it’s a case of running a few commands)
6.	Modify the Ansible inventory file (/etc/Ansible/hosts) and ensure that you have the following host groups with the correct IP’s 
a.	Ha
b.	web
7.	Clone the following files from github
a.	Ha.yaml > /etc/Ansible/
b.	Web.yaml > /etc/Ansible/
c.	/templates/index.html > /etc/Ansible/templates/
d.	/templates/haproxy.cfg > /etc/Ansible/templates/
8.	Use the following commands to run the playbooks and deploy the software/config files
a.	ansible-playbook ha.yaml -i hosts -u vagrant --ask-pass
b.	ansible-playbook web.yaml -i hosts -u vagrant --ask-pass
Test the service by hitting the HAProxy server IP. You should see my static HTML page. 

### Ansible Instrumentation Steps
- Create a directory for the project mkdir ansible-IP
- cd ansible-IP
- Create a custom Vagrantfile using the geerlingguy/ubuntu2004 image
#### Disable SSH host keys checking
- Create a hosts file and type the following:
  - yoloserver ansible_host=127.0.0.1 ansible_port=2222
- Create ansible.cfg file 
  - enter the security settings

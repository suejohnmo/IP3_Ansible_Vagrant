### Ansible Instrumentation Steps
- Create a directory for the project mkdir ansible-IP
- cd ansible-IP
- Create a custom Vagrantfile using the geerlingguy/ubuntu2004 image

#### Disable SSH host keys checking
- Create a hosts file and type the following:
  - yoloserver ansible_host=127.0.0.1 ansible_port=2222
- Display SSH configs using the command vagrant ssh-config and note the port, IdentityFile and user
- Create ansible.cfg file 
  - enter the security settings using the details above. Disable host key checking by typing host_key_checking = False in the file

#### Provision the servers 
- Create a file playbook.yaml that ansible will use to provision the servers listed in the hosts file. 
- Edit the Vagrantfile to use Ansible to provision the servers by adding the below just before the end
  ###### Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
  end

#### Create the virtual servers
- Run the following vagrant commands in the terminal:
  - vagrant up
  - vagrant provision (incase it does not automatically start the playbook)




# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|



#  config.vm.define "ansible" do |ansible|
#   ansible.vm.box = "ubuntu/focal64"
#   ansible.vm.hostname = "ansible"
#   ansible.vm.network "private_network", ip: "192.168.66.1"
#   ansible.vm.synced_folder "./ansible","/home/vagrant/ansible"
#   ansible.vm.provision "file", source: "ssh_keys/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
#   ansible.vm.provision "file", source: "ssh_keys/vagrant_test", destination: "/home/vagrant/.ssh/"
#   ansible.vm.provision "shell", inline: <<-SHELL
#       sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/#g' /etc/ssh/sshd_config
#       service ssh restart
#       curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
#       sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
#       sudo add-apt-repository ppa:ansible/ansible
#       sudo apt update -y && sudo apt -y install sshpass ansible docker-ce docker-compose
#       chmod 600 /home/vagrant/.ssh/vagrant_test
#       chmod 644 /home/vagrant/.ssh/vagrant_test.pub
#   SHELL
 
  
 config.vm.define "server" do |server|
  server.vm.box = "bento/centos-7.9"
  server.vm.hostname = "app"
  server.vm.network "private_network", ip: "192.168.66.66"
  server.vm.network "forwarded_port", guest: 80, host: 8090
  config.vm.provision "file", source: "ssh_keys/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
  config.vm.provision "file", source: "ssh_keys/vagrant_test", destination: "/home/vagrant/.ssh/"
  server.vm.provision "shell", inline: <<-SHELL
    chmod 600 /home/vagrant/.ssh/vagrant_test
    chmod 644 /home/vagrant/.ssh/vagrant_test.pub
    cat /home/vagrant/.ssh/vagrant_test.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL
 end
end
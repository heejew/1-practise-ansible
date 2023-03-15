
For this need your machine (or WSL) with installed ansible and git.
Also, u need add ur sshkey to gitlab for clone test ruby-project

Check vagrantfile and ansible/hosts.ini for sshkeys

Create sshkeys (priv and pub), and copy to folder ssh_keys with names vagrant_test and vagrant_test.pub
```
mkdir ssh_keys
....Well, just create the keys.
```
Up vbox
```
vagrant up
```
Go to playbooks folder

```
cd ansible
```

Install roles and collection
```
ansible-galaxy install -r requirements.yml
ansible-galaxy collection install -r requirements.yml
```

Let's start
```
ansible-playbook playbook.yml -i hosts.ini
```

Welcome to fire hell with up ruby-app


For this need your machine (or WSL) with installed ansible and git.
Also, u need add ur sshkey to gitlab for clone test ruby-project



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

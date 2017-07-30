# Configuration Management tool for setup environment

### How to install ansible
* https://www.linode.com/docs/applications/configuration-management/learn-how-to-install-ansible-and-run-playbooks
* http://docs.ansible.com/ansible/latest/intro_installation.html#latest-releases-via-pi

### First setup target host on ./inventory
```sh
[cloud]
ec2-34-229-88-78.compute-1.amazonaws.com 
```

### For setup unix account in target machine

1. Fill up userinfo in ./group_vars/all/userinfo
```sh
---
my_user: ubuntu   
my_pass: <password>
unix_user: <user_to_be_create>
github_user: <github_account>
github_pwd: <github_passwd>
```
2. Run below command to setup user, you will need to fill user's unix password during the run.
```sh
ansible-playbook setupUser.yml
```
3. Go into your app folder at
```sh
cd ~<username>/apps/RESTAPP
docker-compose up
```

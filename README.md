# Installing AWX with Ansible and Docker
------------

Yes I realize this seems an odd thing to do, but there were a number of steps to get AWX installed and there was "trickiness" around the some of the pip docker packages. Thus, this playbook is born.

The goal of this playbook is to set up a CentOS 7 system so that it is ready for the AWX installer.

## References used in building this playbook and documentation
1. https://www.howtoforge.com/tutorial/centos-ansible-awx-installation/
2. https://docs.docker.com/install/linux/docker-ce/fedora/
3. https://cockpit-project.org/running#centos

## Prerequisites:
- Install a Minimal CentOS 7 system
- Install ansible and some extra utilities
```sh
sudo yum install -y ansible wget nano
```
- Get the playbook
```sh
wget https://xxxxx
```
- Run the playbook
```sh
ansible-playbook playbook.yml -vv --ask-become-pass
```
- Enter your password
- Next, run the ansible installer
```sh
cd /srv/docker/awx/installer
sudo ansible-playbook -i inventory install.yml -vv
```
# Licence
[CC0](./LICENSE.md)

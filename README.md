# Installing AWX with Ansible and Docker
------------

Yes I realize this seems an odd thing to do, but there were a number of steps to get AWX installed and there was "trickiness" around the some of the pip docker packages. Thus, this playbook is born.

The goal of this playbook is to set up a CentOS 7 system so that it is ready for the AWX installer.

## References used in building this playbook and documentation
1. https://www.howtoforge.com/tutorial/how-to-install-ansible-awx-with-docker-on-centos/
2. https://docs.docker.com/install/linux/docker-ce/centos/
3. https://cockpit-project.org/running#centos

## Prerequisites:
- Install a Minimal CentOS 7 system
- Install ansible and some extra utilities
```sh
sudo yum install -y ansible wget nano
```
- Get the playbook
```sh
wget https://raw.githubusercontent.com/javexed/awx-bootstrap/master/playbook.yml
```
- Run the playbook
```sh
ansible-playbook playbook.yml -vv --ask-become-pass
```
---
**NOTE**: I realize that disabling SELinux isn't kosher, but had issues with access to the postgres container. Suggestions to fix are welcome.

---
- Enter your password
- Next, run the ansible installer
```sh
cd /var/lib/awx_installer/installer
sudo ansible-playbook -i inventory install.yml -vv
```
# Licence
[CC0](./LICENSE.md)

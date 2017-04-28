# elk-playground
This is an Ansible project with a development environment powered by Vagrant, to play with ELK, elasticsearch, logstash, beats, kibana and more.

This project sets up:

* 1 virtual machine with centos/7
* ELK-stack and some plugins

This project is intended as a demo/playground for a elk-introductory , teaching git, vagrant and ansible, in the most simple way, and still useable in my classroom. Surely , this playbook can still be improved, but this way it is manageable in my classroom with my students.

## Dependencies

I use as host a Fedora workstation, make sure you have installed :

- vagrant
- vagrant-libvirt
- vagrant-hostmanager
- ansible (ver. 2+)
- git

## Getting started

When cloning, choose a more suiteable  name for the target directory!

```ShellSession
$ git clone https://github.com/belbob/elk-playground.git my-elk-playground
```
After cloning, it's best to remove the `.git` directory and initialise a new repository. The history of the code is most probably irrelevant for your elk-playground project...

### Installation elk-playground with Vagrant

Open a terminal, go to the "my-elk-playground" directory to store this project and issue the following commands:

Edit hosts file and gif a suiteable hostname, only the first hostname will be used by Vagrant.

create the elk-vm

```ShellSession
$ vagrant up
```

### Installation elk-playground with ansible-playbook remote

Create a machine with a CentOS/7 - minimal install. Use this IP-address for the hosts file.

Edit hosts file and gif a suiteable hostname and IP-address.

Add id_rsa.pub key for passwordless login.

```ShellSession
$ ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.xxx.xxx
```

```ShellSession
$ ansible-playbook -i hosts playbook_install_elk.yml --extra-vars "target=see_hosts_file"
```

### Installation glpi-playground on a local machine

Create a updated machine with a CentOS/7 - minimal install. Use use a fix IP-address.

make sure you have installed dependencies:

```ShellSession
# yum -y install epel-release
# yum -y install git ansible
```
clone glpi-playground

```ShellSession
# git clone https://github.com/belbob/elk-playground.git
```
goto glpi-playgroung

```ShellSession
# cd elk-playground
```
Edit hosts file and change the hostname and IP-address before run:

```ShellSession
# ansible-playbook -i hosts -c local playbook_install_elk.yml --extra-vars "target=see_hosts_file"
```

## some issues

If you see only the nginx page, add ip and fqdn to the /etc/hosts file, or even beter, add to your dns-server.

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section. Pull requests are also very welcome. Preferably, create a topic branch and when submitting, squash your commits into one (with a descriptive message).

## License

Licensed under the "GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007". See [LICENSE.md](/License.md) for details.

## Author Information

Written by Robert Keersse (robert.keersse@gmail.com)

Contributions by:

-

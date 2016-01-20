# traffic-control-env

Environment to build Traffic Control CDN Components. Uses Ansible playbooks to download and setup the environment. 

### Traffic Control Build

- Download and Install required software
- Build all components (Not completed)

### Traffic Ops DEV

- Installs all the packages required
- Setup MySQL database
- Simply follow the existing Traffic Ops DEV instruction (needs work!)
- Not quite finished, but useful to see how it can handle cpan.

### Setup - Vagrant

This works great under vagrant in OS X. Only method tested.

- Install Ansible on the Host Server - <http://docs.ansible.com/ansible/intro_installation.html>
- Install Vagrant - <https://www.vagrantup.com/downloads.html>
- Install the Ansible Vagrant plugin `vagrant plugin install ansible`
- Clone the Traffic Control ENV `git clone https://github.com/smalenfant/traffic-control-env.git`
- Clone traffic_control under traffic-control-env and checkout required branch/tag

## Execute Vagrant

### Bring up Vagrant

- `vagrant up rpm-build`

### Login the Vagrant box

- `vagrant ssh rpm-build`
- `cd /vagrant/traffic_control`
- `./build/build.sh <component>`

Files will be available in the Vagrant box as well as the host OS in the <workdir> directory.


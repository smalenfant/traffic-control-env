# traffic-control-env

Environment for setting up Traffic Control

- Installs all the packages required
- Setup MySQL database
- Simply follow the existing Traffic Ops DEV instruction (needs work!)

## Setup

This works great on OS X. That's the only way I tested so far.

- Install Ansible - <http://docs.ansible.com/ansible/intro_installation.html>
- Install Vagrant - <https://www.vagrantup.com/downloads.html>
- Install the Ansible plugin `vagrant plugin install ansible`
- Clone the Traffic Control ENV `git clone https://github.com/smalenfant/traffic-control-env.git`
- You can also clone traffic_control under there too...

```
OSX:traffic-control-env user$ ls -l
total 24
-rw-r--r--   1 smalenfa  staff    65 Oct 16 18:19 README.md
-rw-r--r--   1 smalenfa  staff  1138 Oct 16 18:33 Vagrantfile
-rw-r--r--   1 smalenfa  staff  2867 Oct 19 20:13 traffic-ops.yml
drwxr-xr-x  16 smalenfa  staff   544 Oct 16 18:20 traffic_control
```
- Start the Guest VM `vagrant up traffic-ops-dev`

## What after?

Missing some documentation about the Perl variables needed.

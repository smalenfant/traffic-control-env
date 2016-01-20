# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "bento/centos-6.7"
  #config.vm.box = "bento/centos-7.2"

  # To be used with Traffic Ops RPM
  config.vm.define "traffic-ops-01", primary: true do |box|
   box.vm.hostname = "traffic-ops-dev.kabletown.net"
  end
  
  # Bring up a whole Traffic Ops Development environment
  config.vm.define "traffic-ops-dev", primary: true do |box|
   box.vm.hostname = "traffic-ops-dev.kabletown.net"
  end

  # Used to build all CDN components
  config.vm.define "rpm-build", primary: true do |box|
   box.vm.hostname = "rpm-build.kabletown.net"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "traffic-control.yml"
    ansible.groups = {
      "traffic-ops" => ["traffic-ops-01"],
      "traffic-ops-dev" => ["traffic-ops-dev"],
      "traffic-control-dev" => ["rpm-build"],
      "vagrant:children" => ["traffic-control-dev", "traffic-ops-dev", "traffic-ops"]
    }
  end

end

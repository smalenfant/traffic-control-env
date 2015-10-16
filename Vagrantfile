# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "traffic-ops-dev", primary: true do |to|
   to.vm.box = "bento/centos-6.7"
   to.vm.hostname = "traffic-ops-dev.kabletown.net"
   #to.vm.network "forwarded_port", guest: 443, host: 4443
   #to.vm.network "forwarded_port", guest: 3306, host: 3306
   #to.vm.network "private_network", ip: "192.168.50.3"
   #config.vm.provider :virtualbox do |vb|
   #  vb.customize ["modifyvm", :id, "--memory", "2048"]
   #  vb.customize ["modifyvm", :id, "--cpus", "2"]
   #end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "traffic-ops.yml"
    ansible.groups = {
  #    "cts" => ["cts01"],
      "traffic-ops" => ["traffic-ops-01"],
      "traffic-ops-dev" => ["traffic-ops-dev"],
  #    "chs" => ["chs01", "chs02"],
  #    "crs" => ["crs01", "crs02"],
  #    "edge" => ["ats01", "ats02"],
      "vagrant:children" => ["traffic-ops-dev", "traffic-ops"]
    }
  end

end

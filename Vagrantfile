# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  # config.vm.provider :virtualbox do |vb|
  #   vb.customize ["modifyvm",:id ,"--memory","512"]
  # end

  config.vm.define "webserver" do |webserver|
    webserver.vm.hostname = "webserver"
    webserver.vm.box ="ubuntu/trusty64"
    webserver.vm.network "private_network", ip: "192.168.0.2"
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm",:id ,"--memory","256"]
    end
  end

  config.vm.define "ansible" do |ansible|
    ansible.vm.hostname = "ansible"
    ansible.vm.box ="ubuntu/trusty64"
    ansible.vm.network "private_network" ,ip: "192.168.0.254"
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm",:id ,"--memory","512"]
    end
  end
 config.vm.define "dbserver01" do |dbserver01|
    dbserver01.vm.hostname = "dbserver01"
    dbserver01.vm.box ="ubuntu/trusty64"
    dbserver01.vm.network "private_network", ip: "192.168.0.3"
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm",:id ,"--memory","256"]
    end
  end
  config.vm.define "stage01" do |stage01|
    stage01.vm.hostname = "stage01"
    stage01.vm.box ="ubuntu/trusty64"
    stage01.vm.network "private_network", ip: "192.168.0.5"
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm",:id ,"--memory","256"]
    end
  end

    config.vm.define "zabbix" do |zabbix|
    zabbix.vm.hostname = "zabbix"
    zabbix.vm.box ="ubuntu/trusty64"
    zabbix.vm.network "private_network", ip: "192.168.0.4"
    config.vm.network "forwarded_port", guest: 80, host: 8082
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm",:id ,"--memory","512"]
    end
  end
end
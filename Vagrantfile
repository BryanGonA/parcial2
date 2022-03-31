Vagrant.configure("2") do |config|

if Vagrant.has_plugin? "vagrant-vbguest"
config.vbguest.no_install = true
config.vbguest.auto_update = false
config.vbguest.no_remote = true
#config.vm.network :forwarded_port, guest: 80, host: 1234
#config.vm.network :forwarded_port, guest: 443, host: 1235

end
config.vm.define :cliente do |cliente|
cliente.vm.box = "centos/stream8"
config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
cliente.vm.network :private_network, ip: "192.168.100.9"
#cliente.vm.network "forwarded_port", guest: 81, host: 8080
cliente.vm.hostname = "cliente"
cliente.vm.boot_timeout = 360

end
config.vm.define :firewall do |firewall|
    firewall.vm.box = "centos/stream8"
    config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
    firewall.vm.network :private_network, ip: "192.168.100.10"
    #firewall.vm.network "forwarded_port", guest: 81, host: 8080
    firewall.vm.hostname = "firewall"
    firewall.vm.boot_timeout = 360
    
end
config.vm.define :maestrodns do |maestrodns|
    maestrodns.vm.box = "centos/stream8"
config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
maestrodns.vm.network :private_network, ip: "192.168.100.7"
#maestrodns.vm.network :forwarded_port, guest: 80, host: 1234
#maestrodns.vm.network :forwarded_port, guest: 443, host: 1235
maestrodns.vm.hostname = "maestrodns"

end
config.vm.define :esclavodns do |esclavodns|
    esclavodns.vm.box = "centos/stream8"
config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
esclavodns.vm.network :private_network, ip: "192.168.100.8"
#esclavodns.vm.network :forwarded_port, guest: 80, host: 1234
#esclavodns.vm.network :forwarded_port, guest: 443, host: 1235
esclavodns.vm.hostname = "esclavodns"

end

end

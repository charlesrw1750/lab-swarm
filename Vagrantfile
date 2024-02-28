Vagrant.configure("2") do |config|
    config.vm.provision "shell", inline: "echo config Docker swarm cluster"
    
    config.vm.define "manager" do |manager|
        manager.vm.box = "centos/7"
        manager.vm.hostname = "manager" 
        manager.vm.provision "shell", path: "provision.sh"
        manager.vm.network "private_network", ip: "192.168.1.2"
        manager.vm.network "forwarded_port", guest: 80, host: 8090
        config.vbguest.installer_options = { allow_kernel_upgrade:true }
    end
    
    config.vm.provision "shell", inline: "echo config Docker swarm cluster"
    
    config.vm.define "worker1" do |worker1|
        worker1.vm.box = "centos/7"
        worker1.vm.hostname = "worker1" 
        worker1.vm.provision "shell", path: "provision.sh"
        worker1.vm.network "private_network", ip: "192.168.1.3"
        config.vbguest.installer_options = { allow_kernel_upgrade:true }
    end
    
    config.vm.provision "shell", inline: "echo config Docker swarm cluster"
    
    config.vm.define "worker2" do |worker2|
        worker2.vm.box = "centos/7"
        worker2.vm.hostname = "worker2" 
        worker2.vm.provision "shell", path: "provision.sh"
        worker2.vm.network "private_network", ip: "192.168.1.4"
        config.vbguest.installer_options = { allow_kernel_upgrade:true }
    end
end

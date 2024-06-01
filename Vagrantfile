Vagrant.configure("2") do |config|

  # Define the Server machine
  config.vm.define "server" do |server|
    server.vm.box = "ubuntu/bionic64"
    server.vm.network "private_network", ip: "192.168.10.2", virtualbox__intnet: "lan_net"
    server.vm.hostname = "server"
    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/server.yml"
    end
  end

  # Define the Router machine
  config.vm.define "router" do |router|
    router.vm.box = "ubuntu/bionic64"
    router.vm.network "private_network", ip: "192.168.10.1", virtualbox__intnet: "lan_net"
    router.vm.network "private_network", ip: "192.168.20.1", virtualbox__intnet: "wan_net"
    router.vm.hostname = "router"
    router.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/router.yml"
    end
  end

  # Define the Gateway machine
  config.vm.define "gateway" do |gateway|
    gateway.vm.box = "ubuntu/bionic64"
    gateway.vm.network "private_network", ip: "192.168.20.2", virtualbox__intnet: "wan_net"
    gateway.vm.hostname = "gateway"
    gateway.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/gateway.yml"
    end
  end

  # Define the Remote machine
  config.vm.define "remote" do |remote|
    remote.vm.box = "ubuntu/bionic64"
    remote.vm.network "private_network", ip: "192.168.20.3", virtualbox__intnet: "wan_net"
    remote.vm.hostname = "remote"
    remote.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/remote.yml"
    end

end

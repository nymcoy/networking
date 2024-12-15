Vagrant.configure("2") do |config|

  # Define the Server machine
  config.vm.define "server" do |server|
    server.vm.box = "debian/bookworm64"
    server.vm.network "public_network", bridge: "wlp0s20f3"
    server.vm.hostname = "server"
  end 

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.vault_password_file = ".vault_pass.txt"
  end

end

Vagrant.configure("2") do |config|
  config.vm.define "node1" do |node|
    node.vm.box = "debian/bullseye64"
    node.vm.network "public_network", ip: "192.168.0.5", bridge: "Realtek RTL8822CE 802.11ac PCIe Adapter"
  end
  config.vm.define "node2" do |node|
    node.vm.box = "debian/bullseye64"
    node.vm.network "public_network", ip: "192.168.0.6", bridge: "Realtek RTL8822CE 802.11ac PCIe Adapter"
  end
  config.vm.provision "shell", inline: <<-SHELL
    echo -e "vagrant\nvagrant" | passwd root
    echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
    sed -in 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
    service ssh restart
  SHELL
end
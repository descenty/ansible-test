Vagrant.configure("2") do |config|
  config.vm.define "node1" do |node|
    node.vm.box = "debian/bullseye64"
    node.vm.network "public_network", ip: "192.168.0.5", bridge: "Realtek RTL8822CE 802.11ac PCIe Adapter"
  end
  config.vm.define "node2" do |node|
    node.vm.box = "debian/bullseye64"
    node.vm.network "public_network", ip: "192.168.0.6", bridge: "Realtek RTL8822CE 802.11ac PCIe Adapter"
  end
  config.vm.define "node3" do |node|
    node.vm.box = "debian/bullseye64"
    node.vm.network "public_network", ip: "192.168.0.7", bridge: "Realtek RTL8822CE 802.11ac PCIe Adapter"
    node.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook.yml"
      ansible.inventory_path = "hosts.ini"
    end
  end
end
Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 512
    vb.linked_clone = true
  end
  config.ssh.insert_key = false
  config.vm.define "arq" do |arq|
    arq.vm.hostname = "arq.sergio1.devops"
    arq.vm.network "private_network", ip: "192.168.56.245"
  end
  config.vm.define "db" do |db|
    db.vm.hostname = "db.sergio1.devops"
    db.vm.network "private_network", type: "dhcp"
  end
  config.vm.define "app" do |app|
    app.vm.hostname = "app.sergio1.devops"
    app.vm.network "private_network", type: "dhcp"
  end
  config.vm.define "cli" do |cli|
    cli.vm.hostname = "cli.sergio1.devops"
    cli.vm.network "private_network", type: "dhcp"
    cli.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
    end
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.limit = "all"
    ansible.extra_vars = {
      ansible_python_interpreter: "/usr/bin/python3"
    }
  end
end

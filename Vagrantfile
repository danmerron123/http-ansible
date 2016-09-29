Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"

  config.vm.define "ansible" do |ansible|
    ansible.vm.box = "hashicorp/precise64"
ansible.vm.network "public_network"
ansible.vm.hostname
  end

  config.vm.define "ha" do |ha|
    ha.vm.box = "hashicorp/precise64"
ha.vm.network "public_network"
ha.vm.hostname
  end

  config.vm.define "web1" do |web1|
    web1.vm.box = "hashicorp/precise64"
web1.vm.network "public_network"

  end

  config.vm.define "web2" do |web2|
    web2.vm.box = "hashicorp/precise64"
web2.vm.network "public_network"
  end
end
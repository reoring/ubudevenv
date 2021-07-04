Vagrant.configure("2") do |config|
    
    config.vm.define "dev" do |dev|
      dev.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--macaddress1", "5CA1AB1E0010" ]
      end
      dev.vm.box = "bento/ubuntu-21.04"
      dev.ssh.insert_key = true
  
      dev.vm.provision "ansible" do |ansible|
        ansible.verbose = "v"
        ansible.playbook = "configuration.yaml"
        ansible.host_key_checking = false
      end
  end
end
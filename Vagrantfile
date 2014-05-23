# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/centos-6.5"

  config.vm.network :forwarded_port, guest: 80, host: 8080

  # Ref: http://serverfault.com/a/496612
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end
  
  config.vm.provision :ansible do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "example.yml"
    # ansible.vault_password_file = "vault_pass.txt"
    ansible.raw_arguments = ["--diff"]
    ansible.groups = {
      "local" => ["default"]
    }
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile for installing prerequisites for iiif_s3 gem under
# Ubuntu 18.04
Vagrant.configure("2") do |config|
  # Ansible provisioner default settings
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/iiif_s3.yml"
    ansible.host_vars = {
        :script_vm => {'ansible_python_interpreter' => '/usr/bin/python3'}
    }
    ansible.verbose = ""
  end

  # VirtualBox provider for development environment
  config.vm.define :script_vm do |script_vm|
    script_vm.vm.provider :virtualbox do |vb, override|
      override.vm.box = 'ubuntu/bionic64'
      vb.customize ["modifyvm", :id, "--description", "Created from Vagrantfile in #{Dir.pwd}"]
      vb.memory = 4096
      vb.cpus = 2
      vm_ip = ENV['SCRIPT_VM_IP'] || '10.31.63.5'
      override.vm.network :private_network, ip: vm_ip
    end
  end
end

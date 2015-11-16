# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

file_to_disk = './tmp/opt.vdi'

Vagrant.configure(2) do |config|
  # Vagrant configuration options are fully documented at
  # https://docs.vagrantup.com.

  config.vm.box = "dce-ubuntu-14.04.3-amd64"
  #config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/trusty64/versions/14.04/providers/virtualbox.box"

  # Forwarded port mappings allow access to a specific port on the guest vm
  # from a port on the host machine - to see your vm's port 80, use localhost:8484
  config.vm.network "forwarded_port", guest: 80, host: 8484 # apache
  config.vm.network "forwarded_port", guest: 8080, host: 2424 # tomcat
  # config.vm.network "forwarded_port", guest: 3000, host: 8032 # webrick

  # To share an additional folder to the guest VM, state the path on the host
  # to the actual folder, then the path on the guest to mount the folder. 
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration for VirtualBox:
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    #vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = 2048
    vb.cpus = 2
    # vb.customize ['createhd', '--filename', file_to_disk, '--size', 8 * 1024]
    # vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file_to_disk]
  end

  # Enable provisioning with Ansible
  config.vm.provision "ansible" do |ansible|
    #ansible.verbose = 'vvv'
    ansible.groups = {
      "vagrant" => ["default"],
      "all_groups:children" => ["group1"],
    }
    ansible.extra_vars = {
      deploy_user: "vagrant",
      project_dir: "/vagrant",
      server_name: "localhost",
      rails_env: "production",
      bundle_path: "~/.bundle"
    }
    ansible.playbook = "vagrant-sufia-prod.yml"
    ansible.ask_sudo_pass = true
    # ansible.start_at_task = "services | install postgresql packages"
  end
end

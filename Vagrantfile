Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "ubuntu-vagrant"
  config.vm.synced_folder "storage/", "/var/lib/docker/volumes/", create: true
  
config.vm.provider "virtualbox" do |v|   
  v.memory = 2048   
  v.cpus = 2 
end

  # -= ANSIBLE =-
  # Use :ansible or :ansible_local to provision
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "provisioning/site.yml"
    ansible.install_mode = "pip"
    ansible.version = "2.4.2.0"
  end
end

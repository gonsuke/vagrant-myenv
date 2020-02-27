Vagrant.configure("2") do |config|
  config.vm.box = 'ubuntu/eoan64'
  config.disksize.size = '30GB'
  config.vm.boot_timeout = 600
  config.vm.synced_folder "#{Dir.home}/Documents/projects", "/home/vagrant/projects", create:"true"

  config.vm.provision "ansible_local" do |ansible|
    ansible.become = true
    ansible.playbook = "/vagrant/playbook.yml"
    ansible.install_mode = "pip"
    ansible.compatibility_mode = "auto"

    ansible.extra_vars = {
    }
  end

  config.vm.network "forwarded_port", guest: 2375, host_ip: "127.0.0.1", host: 2375
end


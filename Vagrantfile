Vagrant.configure("2") do |config|
  config.vm.box = 'ubuntu/focal64'
#  config.disksize.size = '30GB'
  config.vm.boot_timeout = 600
  config.vm.synced_folder "#{Dir.home}/Documents/projects", "/home/vagrant/projects", create:"true"

  config.vm.provider 'virtualbox' do |vb|
    vb.memory = '2048'
  end

  config.vm.provision 'ansible_local' do |ansible|
    ansible.become = true
    ansible.playbook = '/vagrant/playbook.yml'
    ansible.install_mode = "pip"
    ansible.compatibility_mode = 'auto'

    ansible.extra_vars = {
    }
  end

  config.vm.network 'forwarded_port', guest: 2375, host_ip: '127.0.0.1', host: 2375   # Docker
  config.vm.network 'forwarded_port', guest: 27017, host_ip: '127.0.0.1', host: 27017 # Mongo
  config.vm.network 'forwarded_port', guest: 19200, host_ip: '127.0.0.1', host: 19200 # Elastic Search
  config.vm.network 'forwarded_port', guest: 8080, host_ip: '127.0.0.1', host: 8080   # Firestore emulator
  config.vm.network 'forwarded_port', guest: 8538, host_ip: '127.0.0.1', host: 8538   # Pubsub emulator
  config.vm.network 'forwarded_port', guest: 6379, host_ip: '127.0.0.1', host: 6379   # Redis
end

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'digital_ocean'
Vagrant.configure('2') do |config|

  config.vm.provider :digital_ocean do |provider, override|
    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    provider.token = 'DIGITAL_OCEAN_API_KEY_GOES_HERE'
    provider.image = 'docker'
    provider.region = 'nyc3'
    provider.size = '512mb'
  end

  config.vm.provision :shell, :inline => <<-EOB
    cd /opt && git clone https://github.com/ab77/netflix-proxy.git && cd netflix-proxy && ./build.sh
  EOB
end
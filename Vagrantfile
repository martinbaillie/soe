# vim: set ft=ruby:fen:fmr={,}:fdl=0:fdm=marker:ff=unix

VM_IP='192.168.4.40'

Vagrant.configure(2) do |config|
  config.vm.box = "martinbaillie/archlinux"
  config.vm.box_check_update = false
  config.vm.hostname = "archie"
  config.vm.network :private_network, ip: VM_IP

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = 8192
    vb.cpus = 4
    vb.name = "archie"
    vb.customize ["modifyvm", :id, "--vram", "64"]
  end

  #config.vm.provision :chef_solo do |chef| 
    #chef.log_level = :debug
    #chef.install = false
    #chef.cookbooks_path = "./chef/cookbooks"
    #chef.roles_path = "./chef/roles"
    #chef.data_bags_path = "./chef/data_bags"

    #chef.add_recipe "xmonad"

    #chef.json = {
      #"apache" => {
        #"listen_address" => "0.0.0.0"
      #}
    #}
  #end

  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = ENV['HTTP_PROXY']
    config.proxy.https    = ENV['HTTPS_PROXY']
    config.proxy.no_proxy = ENV['NO_PROXY']
  end
end

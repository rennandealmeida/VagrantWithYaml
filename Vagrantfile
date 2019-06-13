# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

yaml = YAML.load_file("maquinas.yml")

Vagrant.configure("2") do |config|
  yaml.each do |servidores|
    config.vm.define servidores["name"] do |srv|
      srv.vm.box = servidores["sistema"]
      srv.vm.network "public_network", ip: servidores["ip"]
      srv.vm.hostname = servidores["hostname"]
        srv.vm.provider "virtualbox" do |vb|
          vb.name = servidores["name"]
          vb.memory = servidores["memory"]
          vb.cpus = servidores["cpus"]
        end
      end
    end
end


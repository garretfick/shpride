# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    config.vm.synced_folder ".", "/var/www/public", nfs: true, :mount_options => ['nolock,vers=3,udp,noatime,actimeo=1']

    # Default scotchbox has 2GB of memory - we can use much less
    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
    end

    if defined? VagrantPlugins::HostsUpdater
        config.hostsupdater.aliases = ["shpride.app"]
    end
end

Vagrant.configure("2") do |config|
  config.vm.define "ubuntu_lab" do |lab|
    lab.vm.box = "generic/ubuntu2204"
    lab.vm.box_version = "4.3.12"

    lab.vm.network "private_network", ip: "192.168.100.170"
    lab.vm.network "public_network"
    
    lab.ssh.private_key_path = "~/.vagrant.d/insecure_private_key"
    lab.ssh.insert_key = false
    
    lab.vm.synced_folder "D://HyperV VM//testing", "/vagrant", type: "rsync"

    lab.vm.provider "hyperv" do |h|
      h.vmname = "testing"
      h.memory = "2048"
      h.maxmemory = "4096"
      h.cpus = "2"
      h.enable_virtualization_extensions = true
    end
  end
end

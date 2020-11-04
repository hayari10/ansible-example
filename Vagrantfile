vms = [
    { "name" => "srv1.site1.egfast.com", "ip" => "192.168.33.11" },

    { "name" => "srv1.site2.egfast.com", "ip" => "192.168.33.21" },
    { "name" => "srv2.site2.egfast.com", "ip" => "192.168.33.22" },

    { "name" => "srv1.site3.egfast.com", "ip" => "192.168.33.31" },
    { "name" => "srv2.site3.egfast.com", "ip" => "192.168.33.32" },
    { "name" => "srv3.site3.egfast.com", "ip" => "192.168.33.33" },
]

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false
    vms.each do |host|
        config.vm.define host["name"] do |t|
            t.vm.box = "bento/ubuntu-18.04"
            t.vm.hostname = host["name"]
            t.vm.network(:private_network, ip: host["ip"])
            t.vm.provider "virtualbox" do |v|
              v.memory = host["memory"] || 2048
            end
        end
    end
end

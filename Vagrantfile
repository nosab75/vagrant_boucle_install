# ####################################################################
# ################### CONFIGURATION VARIABLES ########################
# ####################################################################
IMAGE_NAME = "generic/ubuntu1804"   # Image to use
MEM = 2048                          # Amount of RAM
CPU = 1                             # Number of processors
SLAVE_NBR = 2                       # Number of slaves node


Vagrant.configure("2") do |config|
    # RAM and CPU config
     config.vm.provider "virtualbox" do |v|
        #v.gui = true
        v.memory = MEM
        v.cpus = CPU
    end

    # Slave node config
    (1..SLAVE_NBR).each do |i|
        config.ssh.insert_key = false
        config.vm.define "slave-#{i}" do |slave|
            # OS and Hostname
            slave.vm.box = IMAGE_NAME
            slave.vm.box_download_insecure=true
            slave.vm.hostname = "slave-#{i}"
        end
    end
end

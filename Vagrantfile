Vagrant.require_version ">= 1.4.3"
VAGRANTFILE_API_VERSION = "2"

BOX='centos7-standard'
BOX_URL='https://www.dropbox.com/s/hiarmp3cdzjy94o/centos7-standard.box?dl=1'

BOX_OPENSTACK='centos7-openstack'
BOX_URL_OPENSTACK='https://www.dropbox.com/s/oioyoovr1nzvq3c/centos7-openstack.box?dl=1'

os_host= 'os-node1'

ceph_node1= 'ceph-node1'
ceph_node1_disk2 = './ceph-node1/ceph-node1_disk2.vdi' 
ceph_node1_disk3 = './ceph-node1/ceph-node1_disk3.vdi' 
ceph_node1_disk4 = './ceph-node1/ceph-node1_disk4.vdi' 

ceph_node2= 'ceph-node2'
ceph_node2_disk2 = './ceph-node2/ceph-node2_disk2.vdi'
ceph_node2_disk3 = './ceph-node2/ceph-node2_disk3.vdi'
ceph_node2_disk4 = './ceph-node2/ceph-node2_disk4.vdi'

ceph_node3= 'ceph-node3'
ceph_node3_disk2 = './ceph-node3/ceph-node3_disk2.vdi'
ceph_node3_disk3 = './ceph-node3/ceph-node3_disk3.vdi'
ceph_node3_disk4 = './ceph-node3/ceph-node3_disk4.vdi'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

##################################### Configuration for ceph-node1 #####################################################

                 config.vm.define :"ceph-node1" do |node1|
                        node1.vm.box = BOX
                        node1.vm.box_url = BOX_URL
                        node1.vm.network :private_network, ip: "192.168.1.101"
                        node1.vm.hostname = ceph_node1
                        node1.vm.synced_folder ".", "/vagrant", disabled: true

                        node1.vm.provider "virtualbox" do |v|

                                v.customize ["modifyvm", :id, "--memory", "750"]
                                v.name = ceph_node1
				v.gui = true

                                unless File.exist?(ceph_node1_disk2)
                                v.customize ['createhd', '--filename', ceph_node1_disk2, '--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', ceph_node1_disk2]
                                end

                                unless File.exist?(ceph_node1_disk3)
                                v.customize ['createhd', '--filename', ceph_node1_disk3,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 2, '--device', 0, '--type', 'hdd', '--medium', ceph_node1_disk3]
                                end

                                unless File.exist?(ceph_node1_disk4)
                                v.customize ['createhd', '--filename', ceph_node1_disk4,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 3, '--device', 0, '--type', 'hdd', '--medium', ceph_node1_disk4]
                                end

                        end

                end


##################################### Configuration for ceph-node2 #####################################################

 		config.vm.define :"ceph-node2" do |node2|
                        node2.vm.box = BOX
                        node2.vm.box_url = BOX_URL
                        node2.vm.network :private_network, ip: "192.168.1.102"
                        node2.vm.hostname = ceph_node2
                        node2.vm.synced_folder ".", "/vagrant", disabled: true

                        node2.vm.provider "virtualbox" do |v|

                                v.customize ["modifyvm", :id, "--memory", "750"]
                                v.name = ceph_node2
				v.gui = true

                                unless File.exist?(ceph_node2_disk2)
                                v.customize ['createhd', '--filename', ceph_node2_disk2,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', ceph_node2_disk2]
                                end

                                unless File.exist?(ceph_node2_disk3)
                                v.customize ['createhd', '--filename', ceph_node2_disk3,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 2, '--device', 0, '--type', 'hdd', '--medium', ceph_node2_disk3]
                                end

                                unless File.exist?(ceph_node2_disk4)
                                v.customize ['createhd', '--filename', ceph_node2_disk4,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 3, '--device', 0, '--type', 'hdd', '--medium', ceph_node2_disk4]
                                end

                        end

                end

##################################### Configuration for ceph-node3 #####################################################

                config.vm.define :"ceph-node3" do |node3|
                        node3.vm.box = BOX
                        node3.vm.box_url = BOX_URL
                        node3.vm.network :private_network, ip: "192.168.1.103"
                        node3.vm.hostname = ceph_node3
                        node3.vm.synced_folder ".", "/vagrant", disabled: true

                        node3.vm.provider "virtualbox" do |v|

                                v.customize ["modifyvm", :id, "--memory", "750"]
                                v.name = ceph_node3
                                v.gui = true

                                unless File.exist?(ceph_node3_disk2)
                                v.customize ['createhd', '--filename', ceph_node3_disk2,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', ceph_node3_disk2]
                                end

                                unless File.exist?(ceph_node3_disk3)
                                v.customize ['createhd', '--filename', ceph_node3_disk3,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 2, '--device', 0, '--type', 'hdd', '--medium', ceph_node3_disk3]
                                end

                                unless File.exist?(ceph_node3_disk4)
                                v.customize ['createhd', '--filename', ceph_node3_disk4,'--size', 1 * 20480]
                                v.customize ['storageattach', :id,  '--storagectl', 'SATA', '--port', 3, '--device', 0, '--type', 'hdd', '--medium', ceph_node3_disk4]
                                end

                        end

                end

##################################### Configuration for OpenStack node #####################################################

                 config.vm.define :"openstack-node1" do |os|
                        os.vm.box = BOX_OPENSTACK
                        os.vm.box_url = BOX_URL_OPENSTACK
                        os.vm.network :private_network, ip: "192.168.1.111"
                        os.vm.hostname = os_host
                        os.vm.synced_folder ".", "/vagrant", disabled: true

                        os.vm.provider "virtualbox" do |v|

                                v.customize ["modifyvm", :id, "--memory", "4096"]
                                v.name = os_host
                                v.gui = true

                        end
                  end

###############################################################################################################

end

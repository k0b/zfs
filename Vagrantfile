# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :zfs01 do |n1|
	n1.vm.synced_folder ".", "/vagrant", disabled: false
	n1.vm.box = "generic/centos7"
	n1.vm.hostname = "zfs01"
    n1.vm.network :private_network, ip: "192.168.180.33"
	n1.vm.provider "vmware_workstation" do |v1|

	  dir = "/home/kb/vagrant/zfs/1G-disk0"

	  unless File.directory?( dir )
		Dir.mkdir dir
          end

	  file_to_disk = "#{dir}/2G-disk0.vmdk"

	  unless File.exists?( file_to_disk )
		`/usr/bin/vmware-vdiskmanager -c -s 2GB -a lsilogic -t 1 #{file_to_disk}`
	  end

	  swp1 = "/home/kb/vagrant/zfs/1G-swap1"
	  swp2 = "/home/kb/vagrant/zfs/1G-swap2"
	  swp3 = "/home/kb/vagrant/zfs/1G-swap3"
	  swp4 = "/home/kb/vagrant/zfs/1G-swap4"
	  swp5 = "/home/kb/vagrant/zfs/1G-swap5"

      unless File.directory?( swp1 )
		Dir.mkdir swp1
	  end

	  file_to_swap1 = "#{swp1}/1G-swap1.vmdk"

	  unless File.directory?( swp2 )
		Dir.mkdir swp2
	  end

	  file_to_swap2 = "#{swp2}/1G-swap2.vmdk"

	  unless File.directory?( swp3 )
		Dir.mkdir swp3
	  end

	  file_to_swap3 = "#{swp3}/1G-swap2.vmdk"
      
	  unless File.directory?( swp4 )
		Dir.mkdir swp4
	  end

	  file_to_swap4 = "#{swp4}/1G-swap2.vmdk"

	  unless File.directory?( swp5 )
		Dir.mkdir swp5
	  end

	  file_to_swap5 = "#{swp5}/1G-swap2.vmdk"

	  unless File.exists?( file_to_swap1 )
		`/usr/bin/vmware-vdiskmanager -c -s 1GB -a lsilogic -t 1 #{file_to_swap1}`
	  end

	  unless File.exists?( file_to_swap2 )
		`/usr/bin/vmware-vdiskmanager -c -s 1GB -a lsilogic -t 1 #{file_to_swap2}`
	  end

	  unless File.exists?( file_to_swap3 )
		`/usr/bin/vmware-vdiskmanager -c -s 1GB -a lsilogic -t 1 #{file_to_swap3}`
	  end

	  unless File.exists?( file_to_swap4 )
		`/usr/bin/vmware-vdiskmanager -c -s 1GB -a lsilogic -t 1 #{file_to_swap4}`
	  end

	  unless File.exists?( file_to_swap5 )
		`/usr/bin/vmware-vdiskmanager -c -s 1GB -a lsilogic -t 1 #{file_to_swap5}`
	  end


	  v1.vmx["scsi0:1.filename"] = file_to_disk
	  v1.vmx["scsi0:1.present"] = 'TRUE'
	  v1.vmx["scsi0:1.redo"] = ''
	  v1.vmx["scsi0:2.filename"] = file_to_swap1
	  v1.vmx["scsi0:2.present"] = 'TRUE'
	  v1.vmx["scsi0:2.redo"] = ''
	  v1.vmx["scsi0:3.filename"] = file_to_swap2
	  v1.vmx["scsi0:3.present"] = 'TRUE'
	  v1.vmx["scsi0:3.redo"] = ''
	  v1.vmx["scsi0:4.filename"] = file_to_swap3
	  v1.vmx["scsi0:4.present"] = 'TRUE'
	  v1.vmx["scsi0:4.redo"] = ''
	  v1.vmx["scsi0:5.filename"] = file_to_swap4
	  v1.vmx["scsi0:5.present"] = 'TRUE'
	  v1.vmx["scsi0:5.redo"] = ''
	  v1.vmx["scsi0:6.filename"] = file_to_swap5
	  v1.vmx["scsi0:6.present"] = 'TRUE'
	  v1.vmx["scsi0:6.redo"] = ''
	  v1.vmx["memsize"] = 2048
	  v1.vmx["numvcpus"] = 1
      v1.vmx["ethernet.vnet"] = "/dev/vmnet2"
#     v1.vmx["sata0:1.present"] = 'TRUE'
#     v1.vmx["sata0:1.deviceType"] = 'cdrom-image'
#     v1.vmx["sata0:1.fileName"] = '/usr/lib/vmware/isoimages/linux.iso'
#     v1.vmx["ethernet1.addresstype"] = "generated"
#     v1.vmx["ethernet1.connectiontype"] = "nat"
#     v1.vmx["ethernet1.present"] = "TRUE"
#     v1.vmx["ethernet1.virtualdev"] = "e1000"
#     v1.vmx["ethernet2.addresstype"] = "generated"
#     v1.vmx["ethernet2.connectiontype"] = "nat"
#     v1.vmx["ethernet2.present"] = "TRUE"
#     v1.vmx["ethernet2.virtualdev"] = "e1000"
	end
  end
end



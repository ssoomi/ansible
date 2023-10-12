===========================================
              CENTOS STREAM 9
===========================================

- Change STATIC IP ADDRESS:
---------------------------


# cd /etc/NetworkManager/system-connections/
# nano ens18.nmconnection 
# systemctl reload NetworkManager
 
- Change HOSTNAME: 
-----------------

    # hostnamectl set-hostname workstation-C54
 
===========================================
 UBUNTU / DEBIAN
===========================================

- Change STATIC IP ADDRESS:
--------------------------

# eternia@workstation-51:~$ cd /etc/netplan/
# eternia@workstation-51:/etc/netplan$ ls
00-installer-config.yaml.bck  static.yaml
# eternia@workstation-51:/etc/netplan$ nano static.yaml

GNU nano 6.2                         static.yaml                                   

network:
  version: 2
  renderer: networkd
  ethernets:
    ens18:
      addresses:
        - 192.168.x.x/24
      gateway4: 192.168.x.x
      nameservers:
          addresses: [1.1.1.1, 1.0.0.1]
		  
# eternia@workstation-51:/etc/netplan$ netplan apply 

- Change HOSTNAME: 
-----------------

# hostnamectl set-hostname workstation-51

Config Switch 101

Switch>enable
Switch#configure terminal
Switch(config)#hostname SW-101
SW-101(config)#enable secret cisco


SW-101(config)#line console 0
SW-101(config-line)#logging synchronous 
SW-101(config-line)#password cisco
SW-101(config-line)#login
SW-101(config-line)#exit

SW-101(config)#ip domain-name cisco.com
SW-101(config)#ip ssh version 2
SW-101(config)#crypto key generate rsa general-keys modulus 768
SW-101(config)#line vty 0 4
SW-101(config-line)#password cisco
SW-101(config-line)#login
SW-101(config-line)#transport input ssh
SW-101(config-line)#exit

SW-101(config)#service password-encryption


SW-101(config)#banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/

SW-101(config)#vlan 10
SW-101(config-vlan)#name financeiro
SW-101(config-vlan)#exit
SW-101(config)#vlan 20
SW-101(config-vlan)#name rh
SW-101(config-vlan)#exit
SW-101(config)#vlan 99
SW-101(config-vlan)#name mgmt
SW-101(config-vlan)#exit

SW-101(config)#interface vlan 99
SW-101(config-if)#ip address 192.168.99.101 255.255.255.0

SW-101(config)#interface range FastEthernet 0/7 - 8
SW-101(config-if-range)#channel-group 1 mode active
SW-101(config-if-range)#exit
SW-101(config-if-range)#interface port-channel 1
SW-101(config-if)#switchport mode trunk
SW-101(config-if)#switchport trunk allowed vlan 1,10,20,99

SW-101(config)#interface range FastEthernet 0/9 - 10
SW-101(config-if-range)#channel-group 2 mode active
SW-101(config-if-range)#exit
SW-101(config)#interface port-channel 2
SW-101(config-if)#switchport mode trunk 
SW-101(config-if)#switchport trunk allowed vlan 1,10,20,99

SW-101(config-if)#interface range FastEthernet 0/1 - 6
SW-101(config-if-range)#switchport mode access 

SW-101(config)#interface range FastEthernet 0/1 - 3
SW-101(config-if-range)#switchport access vlan 10
SW-101(config-if-range)#exit


SW-101(config)#interface range FastEthernet 0/4 - 6
SW-101(config-if-range)#switchport access vlan 20
SW-101(config-if-range)#exit

SW-101(config)#do wr


Config Switch 102

enable
configure terminal

hostname SW-102

enable secret cisco

line console 0
logging synchronous 
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768

line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/

vlan 10
name financeiro
exit

vlan 20
name rh
exit

vlan 99
name mgmt
exit

interface vlan 99
ip address 192.168.99.102 255.255.255.0

interface range FastEthernet 0/2 - 3
channel-group 1 mode active
exit

interface port-channel 1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,99

interface range FastEthernet 0/1, FastEthernet 0/4
channel-group 3 mode active
description Trunk to SWM-101
exit

interface port-channel 3
switchport mode trunk 
switchport trunk allowed vlan 1,10,20,99

do wr


Config Switch 103

enable
configure terminal

hostname SW-103

enable secret cisco

line console 0
logging synchronous 
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768

line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/

vlan 10
name financeiro
exit

vlan 20
name rh
exit

vlan 99
name mgmt
exit

interface vlan 99
ip address 192.168.99.103 255.255.255.0

interface range FastEthernet 0/1, FastEthernet 0/3
channel-group 2 mode active
description Trunk to SW-101
exit

interface port-channel 2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,99

interface range FastEthernet 0/2, FastEthernet 0/4
channel-group 4 mode active
description Trunk to SWM-101
exit

interface port-channel 4
switchport mode trunk 
switchport trunk allowed vlan 1,10,20,99
exit

do wr

Config Switch SWM-101 

enable
configure terminal

hostname SWM-101

enable secret cisco

line console 0
logging synchronous 
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768

line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/

vlan 10
name financeiro
exit

vlan 20
name rh
exit

vlan 99
name mgmt
exit

interface vlan 99
ip address 192.168.99.104 255.255.255.0
no shut
exit

interface range FastEthernet 0/1, FastEthernet 0/4
channel-group 3 mode active
description Trunk to SW-102
exit

interface port-channel 3
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk allowed vlan 1,10,20,99

interface range FastEthernet 0/2, FastEthernet 0/5
channel-group 4 mode active
description Trunk to SWM-103
exit

interface port-channel 4
switchport trunk encapsulation dot1q
switchport mode trunk 
switchport trunk allowed vlan 1,10,20,99
exit

interface vlan 10
description Default Gateway SVI for 192.168.10.0/24
ip add 192.168.10.1 255.255.255.0
no shut
exit

interface vlan 20
description Default Gateway SVI for 192.168.20.0/24
ip add 192.168.20.1 255.255.255.0
no shut
exit

ip routing 

interface GigabitEthernet 0/1
description routed Port Link to RT-CAMPUS01
no switchport
ip address 192.168.1.1 255.255.255.252
no shut
exit

ip route 192.168.40.0 255.255.255.000 192.168.1.2
ip route 192.168.30.0 255.255.255.000 192.168.1.2
ip route 0.0.0.0 0.0.0.0 192.168.1.2

interface vlan 10
ip helper-address 192.168.1.2

interface vlan 20
ip helper-address 192.168.1.2
exit

do wr

SW-201

enable
configure terminal
hostname SW-201
enable secret cisco

line console 0
logging synchronous
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768
line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/

vlan 30
name administrativo
exit
vlan 40
name alunos
exit
vlan 99
name mgmt
exit

interface vlan 99
ip address 192.168.99.201 255.255.255.0
no shutdown
exit

interface FastEthernet 0/4
switchport mode trunk
switchport trunk allowed vlan 1,30,40,99
exit

interface range FastEthernet 0/1 - 2
switchport access vlan 30
exit

interface range FastEthernet 0/3, FastEthernet 0/5 , FastEthernet 0/6
switchport access vlan 40
exit

do wr

Config do RT 1

enable
configure terminal

hostname RT-Campus01

enable secret cisco

line console 0
logging synchronous 
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768

line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/


interface G0/0/0
ip add 192.168.1.2 255.255.255.252
no shut
exit

interface gigabitEthernet 0/0/1
ip add 10.0.10.1 255.255.255.000
no shut

RT-Campus01(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0/1, changed state to up

RT-Campus01(config-if)#exit

ip route 192.168.10.0 255.255.255.000 192.168.1.1
ip route 192.168.20.0 255.255.255.000 192.168.1.1
ip route 192.168.99.0 255.255.255.000 192.168.1.1
ip route 192.168.40.0 255.255.255.000 10.0.10.2
ip route 192.168.30.0 255.255.255.000 10.0.10.2

ip dhcp excluded-address 192.168.30.1
ip dhcp excluded-address 192.168.40.1
ip dhcp excluded-address 192.168.20.1
ip dhcp excluded-address 192.168.10.1

ip dhcp pool DHCP-VLAN-40
network 192.168.40.0 255.255.255.0
default-router 192.168.40.1

ip dhcp pool DHCP-VLAN-30
network 192.168.30.0 255.255.255.0
default-router 192.168.30.1

ip dhcp pool DHCP-VLAN-20
network 192.168.20.0 255.255.255.0
default-router 192.168.20.1

ip dhcp pool DHCP-VLAN-10
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1


end 

do wr


Config do RT 2

enable
configure terminal

hostname RT-Campus02

enable secret cisco

line console 0
logging synchronous 
password cisco
login
exit

ip domain-name cisco.com
ip ssh version 2
crypto key generate rsa general-keys modulus 768

line vty 0 4
password cisco
login
transport input ssh
exit

service password-encryption

banner motd /####################################
Acesso permitido somente para pessoas autorizadas.
####################################/


interface G0/0/1.30
description Default Gateway for VLAN 30
encapsulation dot1Q 30
ip add 192.168.30.1 255.255.255.0
exit

interface G0/0/1.40
description Default Gateway for VLAN 40
encapsulation dot1Q 40
ip add 192.168.40.1 255.255.255.0
exit

interface G0/0/1.99
description Default Gateway for VLAN 99
encapsulation dot1Q 99
ip add 192.168.99.1 255.255.255.0
exit

interface G0/0/1
description Trunk link to SW-201
no shut
exit 

interface gigabitEthernet 0/0/0
ip address 10.0.10.2 255.255.255.000
no shut

exit

ip route 192.168.10.0 255.255.255.000 10.0.10.1
ip route 192.168.20.0 255.255.255.000 10.0.10.1
ip route 0.0.0.0 0.0.0.0 10.0.10.1

interface G0/0/1.40
ip helper-address 10.0.10.1

interface G0/0/1.30
ip helper-address 10.0.10.1


do wr


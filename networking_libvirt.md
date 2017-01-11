short HOWTO
===========

 - sudo virt-manager
 - right click QEMU/KVM   -or-   Edit -> 'connection details'
 - select tab 'Virtual Networks'

add these 3 networks with networkip:
 - labvms     192.168.4.0/24
 - isolated_1 192.168.100.0/24
 - isolated_2 192.168.101.0/24

# details per network to add:

hit the add button. the + sign.
use Network Name: '$NETWORKNAME'
set network ip to: $NETWORKIP
disable DHCPv4
disable Static Route Definition
click 'Forward'
disable IPv6
select Isolated virtual network

# output command: ip -4 a
4: virbr0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    inet 192.168.122.1/24 brd 192.168.122.255 scope global virbr0
       valid_lft forever preferred_lft forever
9: virbr2: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    inet 192.168.101.1/24 brd 192.168.101.255 scope global virbr2
       valid_lft forever preferred_lft forever
11: virbr1: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    inet 192.168.100.1/24 brd 192.168.100.255 scope global virbr1
       valid_lft forever preferred_lft forever
13: virbr3: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    inet 192.168.4.1/24 brd 192.168.4.255 scope global virbr3
       valid_lft forever preferred_lft forever



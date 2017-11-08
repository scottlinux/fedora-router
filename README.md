fedora-router
=========

Instant home router powered by Fedora Linux!

This playbook provides a simple home router using Fedora Linux

* IPv4 only at the moment
* eth0 is set to receive DHCP from one's ISP
* static LAN assignments can be set in /etc/dnsmasq.conf (future feature for vars)

Requirements
------------

Fedora 27+

Ansible 2.4.0+ to run playbook

Role Variables
--------------

`dns_server_1`            desired DNS server 1 (ex: 8.8.8.8)
`dns_server_2`            desired DNS server 2 (ex: 8.8.4.4)
`lan_subnet_slash_cidr`   desired LAN subnet (ex: 172.16.1.1/24)

Dependencies
------------

Fedora packages: 

    python2-dnf ansible python-firewall git

Example Playbook
----------------

Run playbook to provision a simple router

From inside provisioned host or added to automation:

    ansible-pull -i 'localhost,' -c local -d /tmp/fedora-router -U https://github.com/scottlinux/fedora-router

From one's workstation to then provision a remote VM:

    git clone https://github.com/scottlinux/fedora-router
    ansible-playbook -i "ip.address.of.router," fedora-router/local.yml
    
    
License
-------

MIT

Author Information
------------------

@scottlinux

Credit to @majorhayden https://fedoramagazine.org/build-network-router-firewall-fedora-22-systemd-networkd/



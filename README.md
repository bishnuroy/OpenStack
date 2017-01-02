## OpenStack Newton Setup Guide ##

REF: http://docs.openstack.org/newton/install-guide-rdo/overview.html

#Architecture:

This setup I am doing in 2 nodes.
    a. 1 Controller Node (contoller)-2 Ethernet, 4GB RAM, 2CPU, 50GB Disk.
    b. 1 Compute Node (com1) - 2Ethernet, 6GB RAM, 6CPU, 100GB HDD
    

#Hardware requirements

*Controller*

The controller node runs the Identity service, Image service, management portions of Compute, management portion of Networking, various Networking agents, and the dashboard. It also includes supporting services such as an SQL database, message queue, and NTP.

Optionally, the controller node runs portions of the Block Storage, Object Storage, Orchestration, and Telemetry services.

The controller node requires a minimum of two network interfaces.

*Compute*

The compute node runs the hypervisor portion of Compute that operates instances. By default, Compute uses the KVM hypervisor. The compute node also runs a Networking service agent that connects instances to virtual networks and provides firewalling services to instances via security groups.

You can deploy more than one compute node. Each node requires a minimum of two network interfaces.

*Block Storage*

The optional Block Storage node contains the disks that the Block Storage and Shared File System services provision for instances.
You can deploy more than one block storage node. Each node requires a minimum of one network interface.

*Object Storage*

The optional Object Storage node contain the disks that the Object Storage service uses for storing accounts, containers, and objects.


*Networking*


*Networking Option 1: Provider networks*

The provider networks option deploys the OpenStack Networking service in the simplest way possible with primarily layer-2 (bridging/switching) services and VLAN segmentation of networks. Essentially, it bridges virtual networks to physical networks and relies on physical network infrastructure for layer-3 (routing) services. Additionally, a DHCP service provides IP address information to instances.



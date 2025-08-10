In the file names SITE 1, the Master Repeater must be at 192.168.1.2:50000. There are two peers at SITE 1: Peer1 192.168.1.3:50001 and Peer2 192.168.1.4:50002.
The Rest Channel/Site IP must be 192.168.1.100:55000 at both (all) sites.
IP Remote Programming is also possible but the Device programmer must be configured to use TCP ports 50000 to 50100 (which ought to be the default).

The file SITE 2 is almost the same but there are only two peers: Peer3 192.168.1.2:50003 and Peer2 192.168.1.3:50004.
Since SIT1 and SIT2 are in two different physical subnets, the 192.168.1.0/24 addresses can be reused at each site.

The WAN IP of the SITE1 Router is 10.0.0.1 and for SITE2 it is 10.0.0.1 -  these should be changed to suit your network.

Both Routers have a small block of DHCP addresses in the range between .200 and .254.

Setting up an SSL VPN between two Mikrotik routers involves configuring one as the server and the other as the client using the OpenVPN protocol. Here are two modified scripts, one for each router, that will create the necessary certificates and configurations.

This setup assumes the following:

Router 1 (Server): Public IP 10.0.0.1, Local Network 172.16.1.0/24

Router 2 (Client): Public IP 10.0.0.2, Local Network 172.16.2.0/24

VPN Tunnel Network: 10.0.0.0/24

This script also creates the firewall rules and routes needed to allow traffic to flow between the 172.16.1.0 and 172.16.2.0 networks.

This should get you started! Remember to replace the placeholder IP addresses and networks with your actual configuration. For a production environment, you should also consider stronger ciphers and key sizes. Let me know if you would like me to adjust any of the settings or add more details about how to troubleshoot the connection.

Before you run the SITE 2 (OpenVPN) script, you will need to manually transfer the ca_cert.crt, client_cert.crt, and client_key.key files from the SITE 1 router (10.0.0.1) to the file list on this router!

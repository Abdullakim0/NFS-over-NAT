# NFS-over-NAT

Introduction
Network File System (NFS) allows a system to share directories and files with others over a network. This guide covers the setup and configuration of NFS over NAT (Network Address Translation), 
enabling file sharing across different networks where direct IP addressing is not feasible.

Prerequisites
Two machines (Server and Client) with Linux-based OS.
Both machines should have NFS utilities installed.
Port forwarding configured on the router (to map external IP to the internal IP of the NFS server).

Install NFS Utilities
On both the server and client machines, install the NFS utilities.

Configure NFS Server
Edit the Exports File
Add the directories you want to share to the /etc/exports file on the server.

Start and Enable NFS Service


Configure Port Forwarding on Router
To make the NFS server accessible over the internet, configure port forwarding on your router. Forward the following ports to the internal IP of the NFS server:

Port 2049 (NFS)
Port 111 (RPC)

Adjust Firewall Settings
Ensure that the firewall on the NFS server allows traffic on the NFS and RPC ports.

Configure NFS Client
Create a Mount Point
On the client machine, create a directory where you will mount the NFS share.

Mount the NFS Share
Mount the NFS share using the external IP address of the server.

Verify the Setup
List the contents of the mounted directory to ensure that the NFS share is working correctly.

Make the Mount Permanent
To ensure the NFS share is mounted at boot time, add the following line to the /etc/fstab file on the client.

Troubleshooting
Permission Denied: Ensure the export options are set correctly in /etc/exports and that the client has the necessary permissions.
Mount Failure: Check firewall settings and port forwarding configurations on the router.
Network Issues: Verify that the client can reach the external IP of the server and that the ports are open.

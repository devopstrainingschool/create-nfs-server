# create-nfs-server
Here are the steps and commands for creating an NFS server:

Install the NFS server software:
sql
Copy code
sudo apt-get update
sudo apt-get install nfs-kernel-server -y
Create a directory that will be shared:
bash
Copy code
sudo mkdir /nfs-share
Update the permissions on the shared directory:
bash
Copy code
sudo chmod 777 /nfs-share
Update the NFS exports file to specify which directories should be shared:
javascript
Copy code
sudo nano /etc/exports
Add the following line to the file:

bash
Copy code
/nfs-share  *(rw,sync,no_root_squash)
Restart the NFS server to apply changes:
Copy code
sudo service nfs-kernel-server restart
Verify that the NFS server is running:
Copy code
sudo showmount -e localhost
This should display the shared directory /nfs-share.

## Install on the client
https://www.microhost.com/docs/tutorial/how-to-setup-nfs-server/

links:
https://shishirkh.medium.com/how-to-set-up-an-nfs-for-vms-kubernetes-6e6651d3d85b
https://www.exxactcorp.com/blog/Troubleshooting/deploying-dynamic-nfs-provisioning-in-kubernetes
https://shishirkh.medium.com/how-to-set-up-an-nfs-for-vms-kubernetes-6e6651d3d85b

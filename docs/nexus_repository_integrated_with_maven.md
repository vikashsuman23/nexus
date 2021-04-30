<img src="../images/c4logo.png">

### Steps:
1. Login to your Linux VM and [Install docker](https://github.com/submah/docker-tutorials/blob/master/docker-installation.md)
2. We are going to launch nexus through docker image. Execute the below commands to access nexus UI

```sh
# Create a docker volume

docker volume create local-nexus-data

#Create Nexus Docker Container

docker run -d -p 8081:8081 --name nexus -v local-nexus-data:/nexus-data sonatype/nexus3

```
3. To access nexus UI, Navigate to **IP-address-of-Host_VM:8081**

4.	Login to nexus as admin

**IP-address-of-Host-VM:8081**
Login with username as **admin** and to get password navigate to docker volume **/var/lib/docker/volumes/local-nexus-data/_data/admin.password**

<img src="../images/c4logo.png">

### Steps:

1. Login to you CentOS 7 VM and [Install docker](https://github.com/submah/docker-tutorials/edit/master/install_docker_centos7.md).

2. Create the SSL Certificate

TLS/SSL works by using a combination of a public certificate (.crt) and a private key (.key). The SSL key is kept secret on the server. It is used to encrypt content sent to clients. The SSL certificate is publicly shared with anyone requesting the content. It can be used to decrypt the content signed by the associated SSL key. You should already have the directories **/etc/ssl/certs** and **/etc/ssl/private** to hold the certificates. If not, you have to create them and be able to write to them.

Now, we can create a self-signed key and certificate pair with OpenSSL in a single command by typing:

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-signed.key -out /etc/ssl/certs/nginx-signed.crt

```
<img src="../images/nginx-ssl-certs.png">

3. Pull the Nexus Docker Container 

```
docker pull sonatype/nexus3

```

4. Create a Nexus Docker Container

```
# Create a docker volume

docker volume create local-nexus-data

docker run -d -p 8081:8081 -p 4000:4000 --name nexus -v local-nexus-data:/nexus-data sonatype/nexus3

```

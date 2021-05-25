
cd /etc/yum.repos.d/

vi docker.repo
[Dockerrepo]
name=Docker Repository
baseurl=https://yum.dockerproject.org/repo/main/centos/7
enabled=1
gpgcheck=1
gpgkey=https://yum.dockerproject.org/gpg


yum update -y

yum install docker 

systemctl start docker 

systemctl enable docker

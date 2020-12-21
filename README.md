# install-nginx-repo
install-nginx-repo

# How to install and use Nginx on CentOS 7 / RHEL 7


## Append following for CentOS 7.x:

nano /etc/yum.repos.d/nginx.repo

[nginx]

name=nginx repo

baseurl=http://nginx.org/packages/mainline/centos/7/$basearch/

gpgcheck=0

enabled=1


## Append following for RHEL (Red Hat Enterprise Linux) version 7.x:

[nginx]

name=nginx repo

baseurl=http://nginx.org/packages/mainline/rhel/7/$basearch/

gpgcheck=0

enabled=1


## Install Nginx on CentOS 7

yum install nginx

## Start/stop/restart nginx server

systemctl enable nginx

systemctl start nginx

systemctl stop nginx

systemctl restart nginx

systemctl status nginx

## Open port 80 and 443 using firewall-cmd

sudo firewall-cmd --permanent --zone=public --add-service=http

sudo firewall-cmd --permanent --zone=public --add-service=https

sudo firewall-cmd --reload


## Test it

### Verify that port 80 or 443 opened using ss command:

sudo ss -tulpn

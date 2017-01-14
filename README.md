Install MySQL Database 5.5.x on CentOS 6.8

1.change user to root

su root
2.Install Remi repository

## Remi Dependency on CentOS 6 ##
sudo rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm

sudo rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm

3.Check Available MySQL versions

## Update or Install MySQL 5.5.54(5.5.54-1.el6.remi) ##
yum --enablerepo=remi,remi-test list mysql mysql-devel mysql-server

## CentOS 6.5/6.4/6.3/6.2/6.1/6/5.10 and Red Hat (RHEL) 6.5/6.4/6.3/6.2/6.1/6/5.10 ##
yum --enablerepo=remi,remi-test install mysql mysql-server

## Start MySQL server and autostart MySQL on boot ##
## Fedora 15/14/13/12/11, CentOS 6.5/6.4/6.3/6.2/6.1/6/5.10 and Red Hat (RHEL) 6.5/6.4/6.3/6.2/6.1/6/5.10 ##
/etc/init.d/mysqld start 

## use restart after update## OR ##service mysqld start ## use restart after update 
chkconfig --levels 235 mysqld on

ldconfig -p | grep mysql

gem install mysql2 -v '0.3.17'

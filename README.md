# vps-rum
RUM tests for VPS servers


## CentOS

##### Install EPEL repo
###### CentOS and Red Hat Enterprise Linux 5.x
```
wget http://dl.fedoraproject.org/pub/epel/5/x86_64/epel-release-5-4.noarch.rpm
sudo rpm -Uvh epel-release-5*.rpm
```
###### CentOS and Red Hat Enterprise Linux 6.x
```
wget http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
sudo rpm -Uvh epel-release-6*.rpm
```
###### CentOS and Red Hat Enterprise Linux 7.x
```
wget http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-1.noarch.rpm
sudo rpm -Uvh epel-release-7*.rpm
```
##### Install Cedexis CLI
```
yum install -y python-pip
```

##### Setup Cronjob to run every minute
```
*/1   *    *    *    * /usr/bin/cedexis-radar-cli -c 11475
```

## Ubuntu

TODO

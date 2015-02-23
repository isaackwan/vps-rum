# VPS RUM-ish

This project allows anyone to run performance tests on jsDelivr providers from the command line of a linux server.
Its important because when someone is benchmarking jsDelivr using a synthetic test from a server, our load balancing has no data for that ASN because all of our RUM tests come from residential IPs ASNs. 
This results in worse performance when testing from a server vs a real life user.

To solve this issue the plan is to deploy as much agents as possible to collect performance tests from ASNs used by datacenters.


The following code will install the [open source Cedexis agent](https://github.com/cedexis/cedexis.radar) which is going to collect the same performance information us our [JS tag](https://github.com/jsdelivr/jsdelivr#contribute-performance-data).

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
##### Install Python PIP
```
yum install -y python-pip
```
##### Install Cedexis CLI
```
pip install cedexis.radar
```

##### Setup Cronjob to run every minute
```
*/1   *    *    *    * /usr/bin/cedexis-radar-cli -c 11475
```

##### OR Run the tests manually
```
cedexis-radar-cli -c 11475
```

## Debian/Ubuntu

##### Install Python PIP
```
apt-get install -y python-pip
```
##### Install Cedexis CLI
```
pip install cedexis.radar
```

##### Setup Cronjob to run every minute
```
*/1   *    *    *    * /usr/local/bin/cedexis-radar-cli -c 11475
```

##### OR Run the tests manually
```
cedexis-radar-cli -c 11475
```

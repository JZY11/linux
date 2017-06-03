# Aliyun Ubuntu Configuration

1. Update & upgrade
```
# apt-get update
# apt-get upgrade
```   

2. Install JDK
```shell
# apt-get install python-software-properties
# apt-get install software-properties-common
# add-apt-repository ppa:webupd8team/java
# apt-get update
# apt-get install oracle-java8-installer
```

3. Install Tomcat
```shell
# wget https://mirrors.tuna.tsinghua.edu.cn/apache/tomcat/tomcat-7/v7.0.78/bin/apache-tomcat-7.0.78.tar.gz
# tar xvf apache-tomcat-7.0.77.tar.gz
# cd apache-tomcat-7.0.77/bin
# ./start.sh
```

```shell
# nano apache-tomcat-7.9.77/conf/server.xml
```

```text
8080 to 80
```

```shell
# cd apache-tomcat-7.0.77/bin
# ./shutdown.sh
# ./start.sh
```

4. Install MySQL

```shell
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install mysql-server
```

```shell
sudo nano /etc/mysql/my.cnf
```
```text
[client]
default-character-set=UTF8

[mysql]
default-character-set=UTF8

[mysqld]
character-set-client-handshake = false #force encoding to uft8
character-set-server=UTF8
collation-server=UTF8_general_ci

[mysqld_safe]
default-character-set=UTF8
```
```shell
sudo service mysql stop
sudo service mysql start
mysql -u root -p

show variables like 'char%';
show variables like 'coll%';
```
## install-mariadb

Yum update -y
Sudo yum install mariadb-server
Sudo systemctl start mariadb
Sudo systemctl enable mariadb
sudo mysql_secure_installation

## Login to mysql
mysql -u root -p

## update root user access
update mysql.user set host='%' where user='root';
FLUSH PRIVILEGES;

## select all users and access privileges
SELECT USER,host FROM mysql.user;

## Create a new user and setup access rights and password
CREATE USER 'admin'@'%' IDENTIFIED BY 'root';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%' WITH GRANT OPTION;

## Enable or disable selinux
Vim /ect/selinux/config

## install-mariadb

Yum update -y
Sudo yum install mariadb-server
Sudo systemctl start mariadb
Sudo systemctl enable mariadb
sudo mysql_secure_installation

Mysql -u root -p
Update mysql.user set host=’%’ where user=’root’;
FLUSH PRIVILEGES;

SELECT USER,host FROM mysql.user;

CREATE USER ‘admin’@’%’ IDENTIFIED BY ‘root’;
GRANT ALL PRIVILEGES ON *.* TO ‘admin’@’%’ WITH GRANT OPTION;

Vim /ect/selinux/config

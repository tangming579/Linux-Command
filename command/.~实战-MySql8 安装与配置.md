# MySql 8 安装与配置

yum update

yum install wget

wget http://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm
rpm -ivh mysql80-community-release-el7-1.noarch.rpm
yum -y install mysql  mysql-devel  mysql-server

启动服务：
使用`systemctl start mysqld`命令启动
使用`systemctl status mysqld`查看服务启动状态

开机启动：
systemctl enable mysqld
systemctl daemon-reload

mysql初始密码
cat /var/log/mysqld.log | grep password

firewall-cmd --zone=public --add-port=3306/tcp --permenent

进入客户端：
mysql -u root -p

登录Mysql：“输入mysql -u帐号 -p密码 这是登陆
mysql退出：mysql > exit;
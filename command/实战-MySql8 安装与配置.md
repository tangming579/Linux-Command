# MySql 8 安装与配置

yum update

yum install wget

wget http://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm
rpm -ivh mysql80-community-release-el7-1.noarch.rpm
yum -y install mysql
yum -y install mysql-devel
yum -y install mysql-server

启动服务：
使用`systemctl start mysqld`命令启动
使用`systemctl status mysqld`查看服务启动状态

开机启动：
systemctl enable mysqld
systemctl daemon-reload

mysql初始密码
cat /var/log/mysqld.log | grep password

进入客户端：
mysql -u root -p

修改密码：
ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPass4!';

调整MySQL密码验证规则：（MySql8必须先修改密码）
set global validate_password.policy=0;
set global validate_password.length=4;

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';

开放root远程访问权限
use mysql;
update `user` set `host` = '%' where `user` = 'root';
flush privileges;

开发3306端口：
firewall-cmd --zone=public --add-port=3306/tcp --permanent

重启firewall：
systemctl stop firewalld
systemctl start firewalld

登录Mysql：“输入mysql -u帐号 -p密码 这是登陆
mysql退出：mysql > exit;
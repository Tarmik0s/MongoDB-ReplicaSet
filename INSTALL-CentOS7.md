vi /etc/yum.repos.d/mongodb-org.repo

[mongodb-org-3.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.4.asc

yum -y install mongodb-org

firewall-cmd --permanent --add-port=27017/tcp

systemctl start mongod

systemctl enable mongod

# Centos_MapleStory_079

前言 我发现这东西国内根本没人去折腾都是Windows 下的部署环境教程 

现在的云主机都是超低配，跑Windows的时候特别消耗资源，萌生出在Linux平台下部署冒险岛念头。

系统 Centos7+ Ubuntu18.04+ Debian9+

环境 JDK1.8 JRE1.8 

环境安装参考另一篇文章

首先安装数据库 MySQL 5.5~5.7都行 如果你怕麻烦 就安装宝塔 

导入数据库 ms079_20200629_095607.sql.gz

编辑主目录下的 服务器配置

这是 第四行 ~ 第十一行

# JDBC URL to your database
url = jdbc:mysql://localhost:3306/数据库名?autoReconnect=true&characterEncoding=GBK
wzurl = jdbc:mysql://localhost:3306/数据库名?autoReconnect=true&characterEncoding=GBK

# credentials for database access
user = 数据库用户
password = 数据库密码
timeout = 300000


把数据库用户 数据库密码 数据库名改成你对应的即可


启动命令 必须在 程序目录下 运行

export CLASSPATH=".:dist/*"  && java -server -Dnet.sf.odinms.wzpath=wz server.Start


---
layout: blog
title: Postgres SSL Connection
date_post: 20190408
tags: survey
hidden: true
---

# 問題1
AWSでのpostgresを触ろうとすると次の様なエラーが出てしまった

```
$ psql -U postgres
psql: FATAL:  Peer authentication failed for user "postgres
```

これは理由はあまり調べていないが、面倒くさいので別ユーザーでログインすることにした
```
$ su - postgres
$ psql -U postgres
```
ユーザについてのパスワードを聞かれる。


# 問題2
また、pgAdmin４からpostgresをいじろうと思うと、次の様に拒否らられてしまった。
```
(略) pg_hba.conf rejects connection (略) 
```

[このサイト](http://rina.jpn.ph/~rance/linux/postgresql/connect.html)を参考にpostgresql.confとpg_hba.confに
修正を加えた。
（postgresql.conf）
```
listen_addresses = '*'　←コメントを解除し、''内を * に修正
```
（pg_hba.conf）
```
host all all 0.0.0.0/0 trust
```
その上で再起動した。
```
$ sudo /etc/init.d/postgresql restart
```
ここまでやったらつながりました。

# 問題3
[ec2-user@ip-172-31-37-103 ~]$ sudo service postgresql96 initdb
Initializing database:                                     [  OK  ]
[ec2-user@ip-172-31-37-103 ~]$ sudo /etc/rc.d/init.d/postgresql96 start
Starting postgresql96 service:                             [  OK  ]
[ec2-user@ip-172-31-37-103 ~]$ psql -U postgres
psql: FATAL:  Peer authentication failed for user "postgres"
[ec2-user@ip-172-31-37-103 ~]$ su - postgres
Password: 
su: Authentication failure
[ec2-user@ip-172-31-37-103 ~]$ su - postgres
Password: 
su: Authentication failure
[ec2-user@ip-172-31-37-103 ~]$ sudo su - postgres
Last failed login: Wed May  8 21:34:40 UTC 2019 on pts/0
There were 2 failed login attempts since the last successful login.
-bash-4.2$ psql -U postgres
psql (9.6.11)
Type "help" for help.

postgres=# \q
-bash-4.2$ exit
logout
[ec2-user@ip-172-31-37-103 ~]$ locate postgres| grep init
/etc/rc.d/init.d/postgresql96
/usr/share/doc/postgresql96-9.6.11/html/app-initdb.html
/usr/share/doc/postgresql96-9.6.11/html/catalog-pg-init-privs.html
/usr/share/doc/postgresql96-9.6.11/html/event-trigger-definition.html
/usr/share/doc/postgresql96-9.6.11/html/storage-init.html
/usr/share/doc/postgresql96-9.6.11/html/trigger-definition.html
[ec2-user@ip-172-31-37-103 ~]$ 


# 問題4
なんか適当にインストールすると、パスワードがないユーザーを作ってしまってログインできなくなったりする。
対応方法として'postgres'ユーザーでbashにログインして、ユーザーにパスワードを付与するという方法がある。

* [peer認証の関係でpsqlログインできない時の対処法](https://qiita.com/tomlla/items/9fa2feab1b9bd8749584)

このサイトを参考に作業をしたが、要は'$ su - postgres'でログインして、あれこれ作業するというもの
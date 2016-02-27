#mysql权限控制
`mysql` '权限'

- - -
##理解三张表
mysql.user
mysql.tables.priv
mysql.columns.priv

## 一个命令 grant,赋予权限
所有权限  `all PRIVILEGES`
所有数据库,所有表 `*.*`
用户名 `yang` 登录主机 `localhost`
登录密码 `'yangzie'`
可以给其他用户赋予他的权限 ` WITH GRANT OPTION`
完整语句:
`grant all PRIVILEGES on *.* to yang@localhost IDENTIFIED BY 'yangzie' WITH GRANT OPTION;`
刷新权限,即刻生效
`flush privileges;`
##一个命令 revoke 权限回收
revoke 跟 grant 的语法差不多，只需要把关键字 “to” 换成 “from” 即可


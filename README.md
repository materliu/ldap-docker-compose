# 使用说明
利用此docker-compose配置， 迅速的在本地搭建起ldap服务。

有几点是一定要注意的，mysql的配置需要修改， 设置成使用utf-8的编码格式。

docker-compose up

执行 docker-compose exec ldap /bin/bash 

执行 ldapsearch -x -h localhost -b dc=ldap,dc=dingfudata,dc=com -D "cn=admin,dc=ldap,dc=dingfudata,dc=com" -w XXXXXXXX

来验证ldap服务是不是已经起来了。

输出： 

<pre>
# extended LDIF
#
# LDAPv3
# base <dc=example,dc=org> with scope subtree
# filter: (objectclass=*)
# requesting: ALL
#

[...]

# numResponses: 3
# numEntries: 2
</pre>

就说明成功了， 然后访问： https://localhost:6443  

输入： cn=admin,dc=ldap,dc=dingfudata,dc=com
      XXXXXXXX

登录进Web端的控制台 

ldapsearch -x -h localhost -b dc=ldap,dc=dingfudata,dc=com -D "cn=screwyou,dc=ldap,dc=dingfudata,dc=com" -w screwyou "(&(objectClass=posixAccount)(uid=testldap))"





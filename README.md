![](images/banner.png)


[scans](scans.md)

Domain name:  authority.htb  
DC FQDN: authority.authority.htb  
Alternative DNS: htb.corp.  
IIS 10.0 on port 80.  
PWM v2.0.3 is running on 8443  

[dns](dns.md)

Confirmed domain and FQDN  
Added target as our dns resolver. 

[ntp](ntp.md)

Fixed time skew to avoid problems with kerberos.


> Objective: Account compromise  
> 
> Here we need to compromise any account  in order to get a better understanding of the domain structure. 



[smb](smb.md)

We have access on the Development share that could contain sensitive info. 

![](images/groundzero.png)

We found a few ansible playbooks. Including pwm which had the encrypted AES256 password for the PWM's administration panel.

[pwm](pwm.md)

>  Objective: Account Compromise  
>  
>  We were able to compromise the PWM's admin account by extracting its encrypted password from a ansible playbook and decrypting it with john.
>   
>  After that we're able  to compromise the ldap proxy user svc_ldap by changing some configurations parameters of the PWM service.  




```sh
dig any htb.corp @10.129.229.56
```
![](images/dns.png)

---

**Configuring DNS Resolution For Engagement**

10.129.229.56 htb.corp.  
10.129.229.56 authority.authority.htb. authority  

- /etc/hosts

![](images/hosts.png)

**Let's define a new dns server** 

We don't wanna NetworkManager resetting our configs right?
```sh
sudo systemctl stop NetworkManager
```
```sh
sudo rm -f /etc/resolv.conf
```
```
search htp.corp
nameserver 10.129.229.56
nameserver 1.1.1.1
```
- /etc/resolv.conf

![](images/resolv.png)

This might be needed if you don't want systemd to automatically load NetworkManager and overwrite your settings.
```sh
sudo chattr +i /etc/resolv.conf
```
![](images/immutable.png)

---

**Running a few dns lookups**

![](images/resolution.png)

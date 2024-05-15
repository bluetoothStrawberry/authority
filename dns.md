I was a bit confused by a few results  I got and had to run this step twice.

```sh
dig any authority.htb @10.129.12.250
```
![](images/dns0.png)
```
dig any htb.corp @10.129.12.250
```
![](images/dns1.png)

```
authority.htb.           600    IN      A       10.129.12.250
authority.authority.htb. 3600   IN      A       10.129.12.250
htb.corp.               600     IN      A       10.129.12.250
```

---


**Configuring DNS Resolution For Engagement**

![](images/hosts.png)

**Let's define a new dns server** 

We don't wanna NetworkManager resetting our configs right?
```sh
sudo systemctl stop NetworkManager
```
![](images/resolv.png)


This might be needed if you don't want systemd to automatically load NetworkManager and overwrite your settings.
```sh
sudo chattr +i /etc/resolv.conf
```
![](images/immutable.png)

---

**Running a few tests **

```
dig ns authority.htb
```

![](images/digns.png)

```
nslookup authority
```

![](images/nslookup.png)
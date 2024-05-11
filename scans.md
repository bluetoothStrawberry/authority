
**Host Discovery**
```
sudo nmap -PR -sn -n 10.129.229.56 -oN scans/discovery.txt
```
![discovery](images/discovery.png)

**Open TCP Ports Enumeration**
```
sudo nmap -Pn -n -sS --min-rate=1000 -p- 10.129.229.56 \
	-oN scans/ports.txt
```

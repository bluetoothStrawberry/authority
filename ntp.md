Let's have a loot at the http header to find out target's  time zone
```sh
curl -IL http://10.129.12.250
```
```http
HTTP/1.1 200 OK  
Content-Length: 703  
Content-Type: text/html  
Last-Modified: Tue, 09 Aug 2022 23:00:33 GMT  
Accept-Ranges: bytes  
ETag: "557c50d443acd81:0"  
Server: Microsoft-IIS/10.0  
Date: Sat, 11 May 2024 20:37:30 GMT
```

Okay, it's 20:37:30 GMT. Now we can approximate our clocks.

```sh
sudo date --set="Sat May 11 20:37:43 GMT 2024"
```

Now, we can use the target's ntp service for a perfect sync
```sh
sudo ntpdate -s 10.129.12.250
```

Let's confirm if we've fixed the time skew. 
```sh
sudo nmap -Pn -n -sU -p123 --script=ntp-info.nse 10.129.12.250 \
	-oN scans/ntp.txt
```

![](images/time.png)
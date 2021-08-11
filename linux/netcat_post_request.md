```bash
nc -C lederich.de 80
```

**Input** (line by line):
```text
POST /send-data/dataCollector.php HTTP/1.1
Host: lederich.de
Content-type: application/x-www-form-urlencoded
Content-length: 54
Connection: Close

Humidity=1.1&Temperature_Cel=2.2&Pressure=33.&Heat_Index_Cel=0.4
```

## as one/two liner

```bash
head="POST /send-data/dataCollector.php HTTP/1.1\r\nHost: lederich.de\r\nContent-type: application/x-www-form-urlencoded\r\nContent-length: 54\r\nConnection: Close\r\n\r\nHumidity=1.1&Temperature_Cel=2.2&Pressure=33.&Heat_Index_Cel=0.4\r\n"
echo $head  | nc lederich.de 80
```

## ssl

nc isn't able to handle ssl, but ncat does

ncat -C --ssl lederich.de 443
https://nmap.org/ncat/guide/ncat-ssl.html

1. connect
2. verify server (fingerprint)
3. create http request
HEADER

CONTENT
4. wait for response
5. disconnect

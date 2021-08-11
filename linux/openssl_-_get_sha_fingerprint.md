# linux - get sha fingerprint with openssl

## sha-256

```bash
openssl s_client -connect lederich.de:443 < /dev/null 2>/dev/null | openssl x509 -fingerprint -sha256 -noout -in /dev/stdin
```

**Output**
```text
SHA256 Fingerprint=35:E7:54:CD:09:AD:FC:63:D1:8C:F5:4C:4C:3A:A9:DD:4E:E2:A2:60:6D:83:8B:0D:01:E6:B8:AF:E4:86:46:98
```
## sha-256

```bash
openssl s_client -connect lederich.de:443 < /dev/null 2>/dev/null | openssl x509 -fingerprint -noout -in /dev/stdin
```

**Output**
```text
SHA1 Fingerprint=26:58:C9:99:AE:45:D0:0A:12:A7:48:02:57:CB:CC:A3:62:EB:C4:13
```

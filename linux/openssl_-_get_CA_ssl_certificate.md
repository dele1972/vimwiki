# linux - get CA ssl certificate by openssl

## Version 1

```bash
echo | openssl s_client -servername NAME -connect HOST:PORT |\
  sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > certificate.crt
```

### Substitute

- `NAME` = lederich.de
- `HOST:PORT` = lederich.de:443

### Result

This will download one certificate and create one file:

- `certificate.crt`

### Source

[Get SSL Certificate from Server (Site URL) – Export & Download](https://www.shellhacks.com/get-ssl-certificate-from-server-site-url-export-download/)

## Version 2

```bash
openssl s_client -showcerts -verify 5 -connect HOST:PORT < /dev/null | awk '/BEGIN/,/END/{ if(/BEGIN/){a++}; out="cert"a".pem"; print >out}'; for cert in *.pem; do newname=$(openssl x509 -noout -subject -in $cert | sed -nE 's/.*CN ?= ?(.*)/\1/; s/[ ,.*]/_/g; s/__/_/g; s/_-_/-/; s/^_//g;p' | tr '[:upper:]' '[:lower:]').pem; echo "${newname}"; mv "${cert}" "${newname}"; done
```

### Substitute

- `HOST:PORT` = lederich.de:443

### Result

This will download all certificates and create corresponding files (in my case for lederich.de):

- `banken-sb-beratung_de.pem`
- `r3.pem`

### Source

[How to extract the Root CA and Subordinate CA from a certificate chain in Linux?](https://unix.stackexchange.com/a/487546)

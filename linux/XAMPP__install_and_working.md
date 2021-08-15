# XAMPP

## Download XAMPP

https://www.apachefriends.org/de/download.html

## Installation

1. Change the permissions to the installer

```shell
chmod 755 xampp-linux-*-installer.run
```

2. Run the installer

```shell
sudo ./xampp-linux-*-installer.run
```

## Work with XAMPP

### start

```shell
sudo /opt/lampp/lampp start
```

### stop

```shell
sudo /opt/lampp/lampp stop
```


### start GUI

```shell
cd /opt/lampp
sudo ./manager-linux.run (or manager-linux-x64.run)
```


## XAMPP configuration files

- **Apache**: `/opt/lampp/etc/httpd.conf`, `/opt/lampp/etc/extra/httpd-xampp.conf`
- **PHP**: `/opt/lampp/etc/php.ini`
- **MySQL**: `/opt/lampp/etc/my.cnf`
- **ProFTPD**: `/opt/lampp/etc/proftpd.conf`


## Work with it

To open the Project with `http://localhost/dev/`

### Set a symbolic link to the htdocs folder (`/opt/lampp/htdocs/dev`)

```shell
sudo ln -s -r /home/lederich/dev/web/domains/lederich.de/subdomains/tools/store-web-data /opt/lampp/htdocs/dev
```

### Remove the symbolic link from the htdocs folder (`/opt/lampp/htdocs/dev`)

```shell
sudo unlink /opt/lampp/htdocs/dev
```



docker-compose up -d

docker-compose down



docker-compose logs
docker-compose logs django
docker-compose logs --follow SERVICE
	SERVICE=
		django
		db
		celeryworker
		es
		adminer
		cerebro
		celerybeat
		es-index-creater
		redis
		flower
		tomcat

https://takacsmark.com/docker-logs/

---
less /var/log/cptestX/django (or use 'cat' here)

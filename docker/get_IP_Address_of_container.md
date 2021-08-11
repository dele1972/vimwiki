# get IP Address of container: docker_php-fpm_1

docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' docker_php-fpm_1

or

docker exec -it docker_php-fpm_1 hostname -i

docker-compose up --build
apt remove docker-compose && apt install docker-compose

docker-compose build --no-cache

https://stackoverflow.com/questions/32612650/how-to-get-docker-compose-to-always-re-create-containers-from-fresh-images


waiting for database to be up ...

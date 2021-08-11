sudo apt-get update && sudo apt-get upgrade

sudo apt install docker docker-compose

sudo apt autoremove

docker image ls		# to check a known failure/bug

	n/docker.sock: connect: permission denied

		sudo groupadd docker

		sudo usermod -aG docker $USER	# add current user to group docker

		newgrp docker

		docker image ls

https://github.com/dele1972/docnt-ngpm
http://mysolutions.blog.lederich.de/

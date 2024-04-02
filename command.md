pip freeze > requirements.txt
chmod +x ./endpoint.sh
docker-composer up -d --build
docker exec -it docker /bin/sh

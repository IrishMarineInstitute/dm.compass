# dm.compass
Graphing Interreg Va COMPASS project data

on dmdock02:/home/opsuser/apps/compass
```
docker build -t 127.0.0.1:5000/compass .
docker push 127.0.0.1:5000/compass
docker service create --name compass --label traefik.port=80 --network traefik-net 127.0.0.1:5000/compass
```

# updating the deployment
```
git pull
docker build -t 127.0.0.1:5000/compass .
docker push 127.0.0.1:5000/compass
x=compass;for s in 2 3 4 5 6; do ssh dmdock0$s docker pull 127.0.0.1:5000/$x:latest ; done
service=compass; docker service update --force --image 127.0.0.1:5000/$service:latest $service
```

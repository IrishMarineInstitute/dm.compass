# dm.compass
Graphing Interreg Va COMPASS project data

on dmdock02:/home/opsuser/apps/compass
```
docker build -t 127.0.0.1:5000/compass .
docker push 127.0.0.1:5000/compass
docker service create --name compass --label traefik.port=80 --network traefik-net 127.0.0.1:5000/compass
```

# Notes
### Portainer reset password
```
docker pull portainer/helper-reset-password
docker run --rm -v /var/docker/portainer/data:/data portainer/helper-reset-passwordd
```
path to portainer data in the host masine
>/var/docker/portainer/data

### Docker commands
Create a new docker image from container with id d400e7a849d2
```
docker commit d400e7a849d2 study-checker
```

Use for login in own dockerhub repository
```
docker login
```

If you are already log in in your dockerhub, you can push an image into some repository
```
docker push YOUR_DOCKERHUB_LOGIN/study-checker:1.0 
```

A way to create tar archive for backup/migration docker images.
```
docker save python:2.7.17-alpine3.9 > /path/to/save/my-python-container.tar
```
Use the comand to load archive dockerimage to local dockerregistry
```
docker load < my-python-container.tar
docker images
```
Copy all volumes to the archive with path ./data_vol.tar
```
tar -cvf ./data_vol.tar /var/lib/docker/volumes/data_vol/
```
after it is possible to restor volumes or it is possible to copy on other server and restore right in there. But one more things you should is possible ti do is to raname volumes in corresopnd with your container (use docker inspect comand)

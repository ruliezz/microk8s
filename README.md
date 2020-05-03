# Rubens App
This is a test app for study purpose to understand MicroK8s 

#Build Docker Image
```
docker build -t my-php-app .
```

# Tag and push to private registry
```
docker tag my-php-app ruliezz/microk8:latest
```

```
docker push ruliezz/microk8:latest
```

# Generate secretes for private registry
Example 1 (file):
```
microk8s.kubectl create secret generic regcred --from-file=.dockerconfigjson=/root/snap/docker/423/.docker/config.json --type=kubernetes.io/dockerconfigjson -n ruben
``` 
Example 2 (cmd):
```
microk8s.kubectl create secret docker-registry regcred --docker-server=https://index.docker.io/v1/ --docker-username=<username> --docker-password=<password> --docker-email=<email> -n ruben
```





# matomo on k8s 

### run the following commands on the cluster
```
kubectl create configmap matomo-config --namespace matomo \
--from-literal=MATOMO_DATABASE_HOST=matomo-db-svc \
--from-literal=MATOMO_DATABASE_DBNAME=testdb 

kubectl create secret generic matomo-app-secret --namespace matomo \
--from-literal=MATOMO_DATABASE_USERNAME=dbuser \
--from-literal=MATOMO_DATABASE_PASSWORD=dbusertestpassword 

kubectl create secret generic matomodbsecret --namespace matomo \
--from-literal=MARIADB_ROOT_PASSWORD=rootpassword \
--from-literal=MARIADB_DATABASE=testdb \
--from-literal=MARIADB_USER=dbuser \
--from-literal=MARIADB_PASSWORD=dbusertestpassword

```

### Set up persistent volumes

run the yaml scripts in ```initdeploy``` on the cluster
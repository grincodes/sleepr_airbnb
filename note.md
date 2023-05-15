docker compose up --build for changes on .env file

 @Res({ passthrough: true }) response: Response,
 stops nestjs from automatically sending response

 nestjs sometimes has deps issues 
 run npm up or pnpm up to upgrade all deps to latest
 
 nest info - shows info on the latest version of installed deps

 in k8s folder
 helm create sleepr-aribnb .
 kubectl create deployment reservations --image=us-east1-docker.pkg.dev/containerdemo-365021/reservations/production --dry-run=client -o yaml > deployment.yaml

Run in k8s/sleepr-airbnb folder
helm install sleepr-airbnb .


kubectl create secret docker-registry gcr-json-key --docker-server=us-east1-docker.pkg.dev --docker-username=_json_key --docker-password="$(cat ./sleepr-airbnb-365021-b064d165ed10.json)" --docker-email=designerseyi@gmail.com

kubectl patch serviceaccount default -p '{"imagePullSecrets":[{"name":"gcr-json-key"}]}'

kubectl get po

kubectl get namespaces
kubectl delete deploy dep1 dep2 dep3 --namespace=default



kubectl delete --all deployments --namespace=default
kubectl delete --all pods --namespace=default
kubectl delete --all namespaces


kubectl rollout restart deployment reservations
kubectl logs podsname

kubectl create secret generic mongodb --from-literal=connectionString=mongodb+srv://designerseyi:o6AyqHLeRmKDGtTy@sleepr.d1jxl8o.mongodb.net/

kubectl get secrets

kubectl create service clusterip notifications --tcp=3000 --dry-run=client -o yaml > ./templates/notifications/service.yaml

kubectl create service nodeport reservations --tcp=3004 --dry-run=client -o yaml >./templates/reservations/service.yaml
 
 echo -n "secretkey" | base64 
kubectl edit secret google

switch context
kubectl config get-contexts
kubectl config use-context docker-desktop
kubectl get secrets

Export secrets
kubectl get secret stripe -o yaml >stripe.yaml

Create Secrets from yaml
kubectl create -f stripe.yaml

helm list --all --all-namespaces
helm uninstall <release-name> -n <namespace> --no-hooks

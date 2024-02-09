# node-hostname-k8s
k8s deployable version of node-hostname

# Development lifecycle for the k8s version of node-hostname application
https://github.com/cristiklein/node-hostname

## Clone this repo
git clone https://github.com/jolarsso/node-hostname-k8s.git

## Build containerized version of app

### Build application
npm install

### Build docker image
docker build -t jonteponte71/node-hostname

### Push to docker hub
docker login jonteponte71

docker push jonteponte71/node-hostname

## Deploy application to k8s

### Start minikube
minikube start

### Enable minikube Ingress (optional)
minkube addons enable ingress

### Create deployment
kubectl apply -f k8s/deployment.yaml

### Create service
kubectl apply -f k8s/service.yaml

### Create Ingress (optional if https is needed)
kubectl apply -f k8s/ingress.yaml

### Expose service on minkube
minikube tunnel (in separate terminal)

### Enjoy application at
http://localhost:3000



#Docker  commands recap

docker images
docker run --name springboot-app -p:8080:8080 syedhaseebahmed12/devops-demo-app
docker stop springboot-app

docker rm springboot-app

docker ps
docker images

docker rmi  syedhaseebahmed12/devops-demo-app

Minikube installation Commands

minikube version
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64   && chmod +x minikube
sudo install minikube /usr/local/bin

Start-up Commands

sudo minikube start --vm-driver=none --apiserver-ips 127.0.0.1 --apiserver-name localhost
sudo chown -R $USER $HOME/.minikube
sudo chgrp -R $USER $HOME/.minikube
sudo mv /home/haseeb/.kube /home/haseeb/.minikube $HOME
sudo chown -R $USER $HOME/.kube $HOME/.minikube

kubectl cluster-info

Application running commands

kubectl run springboot-app --image=syedhaseebahmed12/devops-demo-app --port=8080 --image-pull-policy=IfNotPresent
kubectl expose deployment springboot-app --type=NodePort
minikube service springboot-app --url

Cluster Status Commands

kubectl get pods
kubectl get deployments
kubectl get rs
kubectl get nodes

kubectl describe deployments springboot-app

kubectl scale --current-replicas=2 --replicas=3 deployment/springboot-app

Deployment deletions

kubectl delete services springboot-app
kubectl delete deployment springboot-app







Minikube clean-up commands 

minikube stop
sudo minikube delete
sudo rm  -rf /etc/kubernetes
sudo rm -rf ~/.kube && rm -rf ~/.minikube && rm -rf /var/lib/minikube

Other config related commands 

minikube config set embed-certs true

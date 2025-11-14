download minikube

minikube start --driver=docker

kubectl get nodes

#nginx-pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
    - name: nginx
      image: nginx:latest
      ports:
        - containerPort: 80


kubectl apply -f nginx-pod.yaml

kubectl get pods

kubectl describe pod nginx-pod

kubectl port-forward pod/nginx-pod 8080:80

kubectl create deployment my-nginx --image=nginx

kubectl scale deployment my-nginx --replicas=3

kubectl get pods

kubectl set image deployment/my-nginx nginx=nginx:1.25

kubectl expose deployment my-nginx --type=NodePort --port=80

kubectl get svc

minikube service my-nginx –url

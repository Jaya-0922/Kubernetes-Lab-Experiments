EXPERIMENT 1: MULTI-NODE KUBERNETES CLUSTER USING KIND



1\. Check Docker:

docker run hello-world



2\. Check kind:

kind version



3\. Check kubectl:

kubectl version --client



4\. Create project folder:

mkdir $HOME\\k8s-lab1

cd $HOME\\k8s-lab1



5\. Create Kubernetes cluster configuration:

notepad kind-3node.yaml



6\. Create 3-node cluster:

kind create cluster --config kind-3node.yaml



7\. Display cluster nodes:

kubectl get nodes



8\. Display Docker containers:

docker ps



9\. Display control-plane Pods:

kubectl get pods -n kube-system



10\. Deploy nginx with 3 replicas:

kubectl create deployment web --image=nginx --replicas=3



11\. Display Pods:

kubectl get pods -o wide



12\. Watch Pods:

kubectl get pods -w



13\. Delete one Pod to test self-healing:

kubectl delete pod POD\_NAME



14\. Scale deployment to 5 replicas:

kubectl scale deployment web --replicas=5



15\. Scale deployment to 2 replicas:

kubectl scale deployment web --replicas=2



16\. Expose the deployment:

kubectl expose deployment web --port=80



17\. Access nginx:

kubectl port-forward service/web 8080:80



Open browser:

http://localhost:8080


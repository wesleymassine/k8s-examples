# K8S with MySQL and nginx
- To use the k8s localhost install: https://kind.sigs.k8s.io/
- Install kubectl: https://kubernetes.io/docs/tasks/tools/

Example cluster: kind create cluster --config=kind.yaml --name mycluster

# Commands
- PODS
$ kubectl get nodes #list nodes
$ kubectl run ngpod --image=nginx:latest
$ kubectl get pods
$ kubectl get pods –watch
$ kubectl exec –it ngpod – sh
$ kubectl apply –f primeiro-pod.yaml
$ kubectl delete pod [name]
$ kubectl delete –f primeiro-pod.yaml
$ kubectl run -it --image=ubuntu – bash
$ kubectl top pod # show cpumem pods (metrics.server)

- LOGS
$ kubectl get events
$ kubectl get events -n aulainfra
$ kubectl describe pod/mysql -n aulainfra 
$ kubectl describe service/app -n aulainfra
$ kubectl logs mysqldb-0 -n aulainfra

- DEPLOYMENT
$ kubectl get deployments
$ kubectl rollout history deployment deployment-01
$ kubectl apply –f [FOLDER/FILE] –record
$ kubectl annotate deployment deployment-01
kubernetes.io/change-cause=“texto“
$ kubectl rollout undo deployment deployment-01 --to-
revision=1

- Docs: https://kubernetes.io/pt/
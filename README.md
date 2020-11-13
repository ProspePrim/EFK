# EFK
k8s+EFK
1. kubectl create -f kube-logging.yaml
#check: kubectl get namespaces 

2. kubectl create -f elasticsearch-ss.yaml

3.kubectl create -f kibana.yaml

4.kubectl rollout status deployment/kibana --namespace=kube-logging

#check: kubectl get pods --namespace=kube-logging

5.kubectl port-forward kibana-6c9fb4b5b7-plbg2 5601:5601 --namespace=kube-logging

6.kubectl create -f fluentd.yam
#check: kubectl get ds --namespace=kube-logging

references:
1.https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes
2.https://medium.com/@tharangarajapaksha/elk-stack-in-k8s-cluster-13bb509185e0
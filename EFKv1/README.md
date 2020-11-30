# EFK
k8s+EFK
$ helm install elasticsearch stable/elasticsearch wait for few minutes..

$ kubectl apply -f .\fluentd-daemonset-elasticsearch.yaml

$ helm install kibana stable/kibana -f kibana-values.yaml

$ kubectl apply -f .\counter.yaml

references:
https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/getting-started-with-logging-using-efk-on-kubernetes/ba-p/1333050

https://www.youtube.com/watch?v=9dfNMIZjbWg&list=WL&index=1
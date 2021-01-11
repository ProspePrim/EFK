1. Namespace:
    Check namespaces:
        kubectl get namespaces
    
    Create kube-logging:
    kubectl create -f kube-logging.yaml
    
    Check namespaces:
    kubectl get namespaces

2. Install Elasticsearch StatefulSet
    Create service:
        kubectl create -f elasticsearch_svc.yaml
    
    Check:
        kubectl get services --namespace=kube-logging

    Create StatefulSet
        kubectl create -f elasticsearch_statefulset.yaml

    Rollout
        kubectl rollout status sts/es-cluster --namespace=kube-logging

3. Install kibana
    Correct:
        vim kibana.yaml
    
    Install:
        kubectl create -f kibana.yaml
    
    Status:
        kubectl rollout status deployment/kibana --namespace=kube-logging
    
    Check:
        kubectl get pods --namespace=kube-logging

4. Install Fluentd
    Install:
        kubectl create -f fluentd.yaml
    
    Check:
        kubectl get ds --namespace=kube-logging
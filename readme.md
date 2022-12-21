## Actions held to deploy Docker container to Kubernetes and check if it is done correctly:
<ol>
  <li> kubectl apply -f kubernetes.yaml
    
  > deployment.apps/devops-kubernetes created </br>
  > pod/liveness-probe created </br>
  > service/devops-kubernetes-entrypoint created </br>
    
  </li>
  
  <li> kubectl get deployments
   
  > NAME                READY   UP-TO-DATE   AVAILABLE   AGE </br>
  > devops-kubernetes   3/3     3            3           12s </br>
  
  </li>
  
  <li> kubectl get services
  
  > NAME                           TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE </br>
  > devops-kubernetes-entrypoint   NodePort    10.104.157.107   <none>        3000:30001/TCP   31s </br>
  > kubernetes                     ClusterIP   10.96.0.1        <none>        443/TCP          3m17s </br>
  </li>
</ol>

## To tear down application:
kubectl delete -f kubernetes.yaml

> deployment.apps "devops-kubernetes" deleted </br>
> pod "liveness-probe" deleted </br>
> service "devops-kubernetes-entrypoint" deleted </br>

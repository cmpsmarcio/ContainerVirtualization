# Getting Started

## Minikube

First, install [Minikube](https://minikube.sigs.k8s.io/docs/start/)

Get pull of repository to you local computer

After install Minikube, run command bellow in the project folder

```
kubectl apply -f .
```

Check the pods are created and running

```
Kubectl get pods

NAME                               READY   STATUS    RESTARTS   AGE
covid-data-crud-7bd9996f95-885x2   1/1     Running   0          3h13m
mongo-5469b5db88-xdd8x             1/1     Running   0          3h13m
quiz-covid-form-856d6cd94-pqxxh    1/1     Running   0          3h14m
```

Check sevices

```
kubectl get services

NAME              TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)           AGE
covid-data-crud   NodePort    10.102.75.207   <none>        8080:31401/TCP    3h15m
kubernetes        ClusterIP   10.96.0.1       <none>        443/TCP           3h17m
mongo             NodePort    10.96.22.95     <none>        27017:30806/TCP   3h14m
quiz-covid-form   NodePort    10.100.90.40    <none>        3000:30996/TCP    3h15m
```

## Services

Run the commands below to start api and frontend services

```
kubectl port-forward service/covid-data-crud 8080:8080
```

Open new terminal and run commmand

```
kubectl port-forward service/quiz-covid-form 3000:3000

```

## Frontend & API

Quiz
- http://localhost:3000

List
- http://localhost:3000/list

Api Swagger

- http://localhost:8080/swagger-ui/index.html?configUrl=/api-docs/swagger-config#/

# Udacity udagram kubernetes

[![Build Status](https://api.travis-ci.com/jsricarde/udacity-udagram-kubernetes.svg?branch=master)](https://travis-ci.com/github/jsricarde/udacity-udagram-kubernetes)

## setup credentials
Configure the your aws and env variables in `env-secret.yaml`, `aws-secret.yaml`, `env-configmap.yaml` inside the `udacity-c3-deploymen/k8s` directory:

## use docker to run the application locally
Run the next commands to up the application locally:

```bash
docker-compose -f docker-compose-build.yaml build
docker-compose up
```

## docker hub images
You can view all the images of the project in my hub account

- https://hub.docker.com/repository/docker/sricarde/reverseproxy
- https://hub.docker.com/repository/docker/sricarde/udacity-frontend
- https://hub.docker.com/repository/docker/sricarde/udacity-user
- https://hub.docker.com/repository/docker/sricarde/udacity-feed

## setup kubernetes
To run kubernetes you need to setup a cluster in [AWS-EKS], after that you need to run the following commands:
```bash
aws --region <region> eks update-kubeconfig --name <cluster_name> --role-arn arn:aws:iam::<aws_account_id>:role/<role_name>
```
```bash
kubectl get nodes
```

After that you can run each service and deployment image in the `/deployments/k8s/` directory with the following commands:

```bash
- kubectl apply -f <service-file-names>
- kubectl apply -f <deployment-file-names>
- kubectl get pods
- kubectl get svc
- kubectl get deployments
```

## travis CI/CD
The `.travis.yml` is located in the root direcorty of the project and you can see correctly configure in my travis account  [travis].


   [AWS-EKS]: <https://docs.aws.amazon.com/eks/latest/userguide/getting-started-console.html>
   [travis]: <https://travis-ci.com/github/jsricarde/udacity-udagram-kubernetes>

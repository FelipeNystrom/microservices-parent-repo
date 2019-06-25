# A basic microservice system

This is the parent repo for a small microservice project. It consists of four small services written in Nodejs.

- [api gateway service](https://github.com/FelipeNystrom/api-gateway)
- [user and authentication service](https://github.com/FelipeNystrom/auth-user-sevice)
- [post service](https://github.com/FelipeNystrom/post-service)
- [image upload service](https://github.com/FelipeNystrom/image-and-video-API)

_Kubernetes migration_

The whole system consists of a postgres db service, for interservice communication a kafka messagebus service together with zookeeper for orchestration of future kafka instances is in place.

The kafka setup is for learning purpose and is as of now not production ready. The goal however is to take this whole system and make it ready for production. A nginx reverse proxy sits in front of everything and pushes incoming requests to the api gateway.

Generate key pair and put in .env file

```
# Generate 4096 bit Private key
$ openssl genrsa -out myprivate.pem 4096
```

```
# Separate the public part from the Private key file.
$ openssl rsa -in myprivate.pem -pubout > mypublic.pem
```

I'm using the [nginx ingress controller](https://github.com/kubernetes/ingress-nginx). Read the deployment docu [here](https://kubernetes.github.io/ingress-nginx/deploy/) for setup instructions.

To setup the ingress controller run the command

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/mandatory.yaml
```

I use rook-ceph for storage. To set this up use the following commands in top-down order:

```
kubectl apply -f https://raw.githubusercontent.com/rook/rook/master/cluster/examples/kubernetes/ceph/common.yaml
```

```
kubectl apply -f https://raw.githubusercontent.com/rook/rook/master/cluster/examples/kubernetes/ceph/operator.yaml
```

```
kubectl apply -f https://raw.githubusercontent.com/rook/rook/master/cluster/examples/kubernetes/ceph/cluster-minimal.yaml
```

To setup a storage class in a test environment run the command:

```
kubectl apply -f https://raw.githubusercontent.com/rook/rook/master/cluster/examples/kubernetes/ceph/storageclass-test.yaml
```

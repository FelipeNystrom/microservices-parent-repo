# A basic microservice system

This is the parent repo for a small microservice project. It consists of four small services written in Nodejs.

- [api gateway service](https://github.com/FelipeNystrom/api-gateway)
- [user and authentication service](https://github.com/FelipeNystrom/auth-user-sevice)
- [post service](https://github.com/FelipeNystrom/post-service)
- [image upload service](https://github.com/FelipeNystrom/image-and-video-API)

Every service is containerized with docker and is handled through docker compose. The whole system further consists of a postgres db service, for interservice communication a kafka messagebus service togheter with zookeeper for orchestration of future kafka instances is in place.

The kafka setup is for learning purpose and is as of now not production ready. The goal however is to take this whole system and make it ready for production. A nginx reverse proxy sits in front of everything and pushes incoming requests to the api gateway.

Every nodejs service exposes by default port **_9229_** to be able to connect to node inspector.

Build microsevice system.

```
    docker-compose --build
```

Take down microservices

```
    docker-compose down
```

Bring back microservices

```
    docker-compose down
```

**_This project is still under construction with the aim to make it production ready. Feel free to make a pull request_**

### TODO:

- [ ] Migrate to Kubernetes
- [ ] Monitor service with heartbeat checks on every service.
- [ ] Wait-for db and kafka complete startup functionality

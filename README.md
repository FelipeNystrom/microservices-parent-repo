# A basic microservice system

This is the parent repo for a small microservice project. It consists of four small services written in Nodejs.

- [api gateway service](https://github.com/FelipeNystrom/api-gateway)
- [user and authentication service](https://github.com/FelipeNystrom/auth-user-sevice)
- [post service](https://github.com/FelipeNystrom/post-service)
- [image upload service](https://github.com/FelipeNystrom/image-and-video-API)

Every service is containerized through docker. Except the four services mentioned above this system further consists of a postgres db and a a kafka messagebus service for interservice communication togheter with zookeeper for orchestration of kafka brokers.

You can find the diffrent implementations in diffrent branches _as of now it consists of a kubernetes branch and a docker compose branch_.

**_This project is still under construction with the aim to make it production ready. Feel free to make a pull request_**

### TODO:

- [ ] Migrate to Kubernetes
- [ ] Monitor service with heartbeat checks on every service.
- [ ] Wait-for db and kafka complete startup functionality

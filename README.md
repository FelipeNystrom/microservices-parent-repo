# A basic microservice system

This is the parent repo for a small microservice project. It consists of four small services written in Nodejs.

- api gateway service: [docker-compose version](https://github.com/FelipeNystrom/api-gateway), [kubernetes version](https://github.com/FelipeNystrom/kubernetes-api-gateway)
- [user and authentication service](https://github.com/FelipeNystrom/auth-user-sevice)
- [post service](https://github.com/FelipeNystrom/post-service)
- [image upload service](https://github.com/FelipeNystrom/image-and-video-API)

Every service is containerized through docker. The project is designed to be as generic as possible to offer base functinality to build. The system contains of the four services mentioned above, a postgres db instance and a kafka messagebus service for interservice communication together with zookeeper for orchestration of kafka brokers.

You can find the diffrent implementations in diffrent repos _as of now it consists of two different setups: [kubernetes setup](https://github.com/FelipeNystrom/kubernetes-setup) and a [docker compose setup](https://github.com/FelipeNystrom/docker-compose-setup)_.

**_This project is still under construction with the aim to make it production ready. Feel free to make a pull request in specific repo_**

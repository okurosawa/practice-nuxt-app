# Project setup
## Build image and run docker container
```shell
docker-compose up -d --build
```
## Install node modules
```shell
docker-compose exec app sh
npm i
```
## Start your development
```shell
npm run dev
```
## For production
```shell
npm run prod
```
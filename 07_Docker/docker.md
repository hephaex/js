i# Docker
* 가벼운 가상화 환경
* Build once, run anywhere
* [공식사이트](www.docker.io)
* 필요지식
 - Unix/Linux
 - Vagrant
* 환경 CoreOS -> Docker

## vagrant setting
* wget https://github.com/hephaex/coreos/Vagrantfile
* vagrant up
* vagrant ssh
* export DOCKER_HOST=tcp://localhost:2375

## Understand docker flow
* base: Docker installed OS (CoreOS, Ubuntu, Radhat7.0)
* docker pull: Create Image
* docker run: Container execution
* docker commit: Image fixed
* docker push: Push image into Docker index
* Another machine docker pull from Docker index
* Another machine docker run builed image


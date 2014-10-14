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

## Docker index.
* [site](index.docker.io)
* docker search centos
```
core@core-01 ~ $ docker search centos
NAME                                            DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
centos                                          The official build of CentOS.                   514       [OK]

...
```

* docker images
```
core@core-01 ~ $ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
centos              centos6             68edf809afe7        12 days ago         212.7 MB
```

* docker inspect centos:centos6
```
core@core-01 ~ $ docker inspect centos:centos6
[{
    "Architecture": "amd64",
	"Author": "The CentOS Project \u003ccloud-ops@centos.org\u003e - ami_creator",
	"Comment": "",
	"Config": {
 	    "AttachStderr": false,
		"AttachStdin": false,
		"AttachStdout": false,
		"Cmd": null,
		"CpuShares": 0,
		"Cpuset": "",
		"Domainname": "",
		"Entrypoint": null,
		"Env": [
		    "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
		],
		"ExposedPorts": null,
		"Hostname": "fbfb1f83a702",
		"Image": "5b12ef8fd57065237a6833039acc0e7f68e363c15d8abb5cacce7143a1f7de8a",
		"Memory": 0,
		"MemorySwap": 0,
		"NetworkDisabled": false,
		"OnBuild": [],
		"OpenStdin": false,
		"PortSpecs": null,
		"StdinOnce": false,
		"Tty": false,
		"User": "",
		"Volumes": null,
		"WorkingDir": ""
	},
	"Container": "fbfb1f83a7026af1e1a58626c52bf94e5cc1cf239feddd495adb955c6939ace0",
	"ContainerConfig": {
	    "AttachStderr": false,
		"AttachStdin": false,
		"AttachStdout": false,
		"Cmd": [
		"/bin/sh",
		    "-c",
			"#(nop) ADD file:39864126259d42f79cafa1be5f9d8a0e3e05032ac7ce275bd99ba4db5762e70e in /"
		],
		"CpuShares": 0,
		"Cpuset": "",
		"Domainname": "",
		"Entrypoint": null,
		"Env": [
		    "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
		],
		"ExposedPorts": null,
		"Hostname": "fbfb1f83a702",
		"Image": "5b12ef8fd57065237a6833039acc0e7f68e363c15d8abb5cacce7143a1f7de8a",
		"Memory": 0,
		"MemorySwap": 0,
		"NetworkDisabled": false,
		"OnBuild": [],
		"OpenStdin": false,
		"PortSpecs": null,
		"StdinOnce": false,
		"Tty": false,
		"User": "",
		"Volumes": null,
		"WorkingDir": ""
	},
	"Created": "2014-10-01T20:46:32.276898162Z",
	"DockerVersion": "1.2.0",
	"Id": "68edf809afe78e6c2460fb4b339e4f4f9298b765a21a55d34c302e9d185c2bc0",
	"Os": "linux",
	"Parent": "5b12ef8fd57065237a6833039acc0e7f68e363c15d8abb5cacce7143a1f7de8a",
	"Size": 212697787
	}
]
```

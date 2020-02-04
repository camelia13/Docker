# Docker

## Setup

```shell
$ sudo apt update
$ sudo apt apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
$ sudo apt update
$ apt-cache policy docker-ce
```

```shell
sudo apt install docker-ce
```

도커가 정상적으로 실행 중인지 확인
```shell
sudo systemctl status docker
```

Got permission denied while trying to connect to the Docker daemon socket 에러 발생 시 docker.sock에 모든 유저(chmod 666)에 permission을 주면 된다. 아니면 아래 코드처럼 permission을 docker 그룹만 갖도록 설정하면 된다. 
```shell
sudo chmod 666 /var/run/docker.sock
# sudo chown root:docker /var/run/docker.sock
```

그 이후는 아래의 코드로 이미지를 받아 도커 컨테이너를 사용할 수 있다.
```shell
docker pull image
```

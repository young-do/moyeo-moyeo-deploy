# 모여모여 배포용 repo

> 모여모여 한큐에 띄우자

모여모여 서비스를 ec2 환경과 같은 단일 서버 인스턴스에 docker, docker-compose를 이용해 한번에 띄울 수 있도록 구성한 repo

## 알면 좋은 지식?

- docker, docker-compose
- git submodule
- shell script

## Prerequisite

docker와 docker-compose가 설치되어 있어야 함
아래의 순서로 설치하면 됨

```
# 출처: https://narup.tistory.com/278
# docker 설치
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker

# docker-compose 설치
sudo curl -L "https://github.com/docker/compose/releases/download/v2.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version
```

## Setup

ec2 와 같은 server 인스턴스에 배포하는 경우 아래 순서로 진행

1. server 인스턴스 접속 후
2. git clone
3. clone한 디렉토리로 이동
4. `git submodule init` 실행
5. `git submodule update` 실행
6. `chmod +x ./moyeo-init.sh` 실행
7. `./moyeo-init.sh` 실행
8. `docker-compose up --build -d` 실행
9. 종료하고 싶다면 `docker-compose down` 실행

## Update

각 레포의 업데이트가 발생한 경우 아래의 명령어 실행

```
git submodule update --remote
```

## Setup https

(TODO)

## Cleanup

서버 종료 후 db 삭제를 원할 경우 아래의 명령어 실행

```
chmod +x ./moyeo-cleanup.sh
./moyeo-cleanup.sh
```

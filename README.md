# 모여모여 배포용 repo

모여모여 frontend, backend 레포를 git 서브모듈를 활용하여
docker-compose로 한번에 띄울 수 있도록 구성함

## Setup

ec2 와 같은 server 인스턴스에 배포하는 경우 아래 순서로 진행

1. server 인스턴스 접속 후
2. git clone
3. clone한 디렉토리로 이동
4. `git submodule init` 실행
5. `git submodule update` 실행
6. `chmod +x ./moyeo-init.sh` 실행
7. `./moyeo-init.sh` 실행
8. `docker-compose up --build -d` 실행 (로그를 실시간으로 보고 싶다면, `-d` 옵션 제거해서 실행)
9. 종료하고 싶다면 `docker-compose down` 실행 (`-d` 옵션 제거해서 실행했다면 ctrl+c 로 종료)

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

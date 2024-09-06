# 모여모여 배포용 repo

모여모여 frontend, backend 레포를 git 서브모듈를 활용하여
docker-compose로 한번에 띄울 수 있도록 구성함

## Todo (앞으로 작성해야하는 것들)

- 초기 셋팅
- 인증서 연결하기
- 서버 실행하기
- 서버 종료하기
- 각 레포 업데이트 반영하기

## setup

```
# 프론트엔드 레포를 서브모듈로 추가
git submodule add https://github.com/Nexters/moyeo-moyeo-FE.git frontend

# 백엔드 레포를 서브모듈로 추가
git submodule add https://github.com/Nexters/moyeo-moyeo-BE backend
```

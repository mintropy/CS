# Docker 명령어
**tags** : #programming  #Docker 

## build
- `docker build <옵션>`
	- --tag : 이미지 태거 설정
		- `docker build --tag image:0.1 .`
	- . 은 dockerfile의 위치 지정

## run
- `docker run <옵션> <이미지> <명령어> <인자>`
	- -d : 백그라운드에서 실행하는 옵션, detached 모드
	- --name : 컨테이너 ID보다 이름을 부여하여 식별 할 수 있도록 함
	- -p : 포트 배포, 바인드를 위해 사용

## images
- `docker images`
- 모든 이미지 목록 확인

## ps
- `docker ps`
- 모든 컨테이너 목록 확인

## stop
- `docker stop <컨테이너 이름>`
- 컨테이너 정지

## start
- `docker start <컨테이너 이름>`
- 정지한 컨테이너 재실행

---
- rm : 컨테이너 삭제
- rmi : 이미지 삭제

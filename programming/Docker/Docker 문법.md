# Docker 문법
**tags** : #programming  #Docker

## FROM <이미지>:<태그>
- Base Container image 지정
	- Base Images : https://hub.docker.com/search?q=&type=image&image_filter=official
	- 기본 이미지를 사용하여 도커를 구축하는데 사용

## WORKDIR <경로>
- container내에서 working directory 경로 지정

## RUN <커맨드>
- 또는 [<커맨드> <파라미터> <파라미터>] 형식으로 형식으로 지정 가능
- shell, bash 등에서 실제 명령어를 동작하는 역할
- 특정 소프트웨어 및 언어에 따라 다음과 같이 작성 가능
	- `RUN apk add curl`
	- `RUN npm install --silent`
	- `RUN pip install -r requirements.txt`

## COPY <src> <dest>
- 컨테이너 파일 시스템에 파일 및 폴더를 복사
	- 파일 및 폴더이름, 위치 순서로 입력

## CMD <커맨드>
- 실제 container 구동시 실행될 명령어
- CMD 커맨드가 길어지는 경우 ENTRYPOINT 명령문과 함께 사용
	- `CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]`

## EXPOSE <포트>
- 호스트와 연결할 포트 번호 설정
- docker run 명령에서 --expose 옵션과 동일

# 참조
- https://docs.microsoft.com/ko-kr/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile
- https://rajent.tistory.com/entry/Dockerfile-%EB%AC%B8%EB%B2%95-%EC%A0%95%EB%A6%AC
- https://www.daleseo.com/dockerfile/
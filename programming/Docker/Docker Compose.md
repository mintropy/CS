# Docker Compose
**tags** : #programming  #Docker 
- 복수의 컨테이너를 실행시키기위한 Compose, 툴
	- [Docker](Docker.md)
- YAML 파일을 사용하여 구성할 수 있음
- 다음과 같은 단계를 거쳐서 정의 및 사용
	- Dockerfile 정의
	- docker-compose.yml에서 구성할 서비스 정의
	- docker-compose up명령어로 compose 시작 및 서비스 시작

## Compose 파일 만들기
- https://docs.microsoft.com/ko-kr/visualstudio/docker/tutorials/use-docker-compose
### 프로젝트 루트에 docker-compose.yml 생성
- Compose 파일에 스키마 버전 정의

```YAML
version: "3"
```

- https://docs.docker.com/compose/compose-file/
- https://meetup.toast.com/posts/277

### App Service 정의
```YAML
services:
  app:
    image:
	command:
	ports:
	working_dir:
	volumes:
	enviromnet:
```

- services 내부에서 각 서비스 정의
- 각 서비스는 image, command, ports 등 정보를 정의

## Compose 실행
- Docker와 비슷하게 빌드 및 실행
- `docker-compose build` 를 통하여 각 컨테이너 빌드
- `docker-compose up` 을 통하여 컨테이너 실행

## docker란?

도커는 어플리케이선을 패키징 할수있는 툴이다.

container라는 불리는 하나의 작은 소프트웨어 유닛 한에 우리 어플리케이션과 그 필요한 시스템, 환경설정 모든 디펜더시를 하나로 묶어서 배포할수있다.

docker container 안에는 어플리케이션이 구동하기 위한 모든것들을 설정할수있다는것이다.

## docker의 구성

container를 만들기 위해 총 3가지

### Dockerfile - 컨테이너 만드는 설명서

### Image - 우리 어플리케이션을 실행하는데 피룡한 코드, 런타임 환경 즉, 스냅샷해서 이미지로 만들어준다.

### Container - 컨테이너는 샌드박스처럼 우리가 캡쳐한 이미지를 고립된 환경에서 어플리케이션이 동작하는것이다.

즉 Image는 class라고 생각하면 되는것이다.

---

Dockerfile

```
FROM node:20.7.0

WORKDIR /app  // app안에 모든 것을 할것이다.

COPY . .

RUN npm install  // npm i를 실행한다.

RUN npm ci //이것을 사용하면 우리 프로젝트 버전을 그대로 유지 가능하다

RUN npm install -g serve

RUN CI='false' npm run build

ENTRYPOINT ["serve", "-s", "build"]
```

// build 명령어
docker build -f Dockerfile -t fun-docker .
docker run -d -p 8080:8080 fun-docker
docker ps
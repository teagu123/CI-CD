## Github Action 이란?

- 소프트웨어 workflow를 자동화할 수 있도록 도와주는 도구
- public repo는 무료지만, limit가 존재한다

---

## Github Action 내용 설명

Workflow, Event, Job, Step, Action, Runner 등이 있음

### Workflow는?

- 가장 최상위 개념
- 여러개의 job으로 구성되어있고, Event에 의해 트리거될 수있는 자동화된 프로레스
- Workflow 파일은 Github repo에서는 .github/workflows 폴더 아래에 저장됨

### Event란?

- workflow를 실행하는 특정 활동 혹은 규칙
- 특정 브랜치로 Push
- 특정 브랜치고 PR

### Job이란?

- 이건 step으로 구성되어있다. 가상 환경의 인스턴스에서 실행
- 다른 job에 의존 관계를 가실 수 있도, 독립적으로 병렬 실행 가능

### Step

- Task들의 집합으로, 커맨드를 날리거나 action을 실행할 수 있음.

### Action

- Workflow의 가장 작은 블럭이다.
- Job을 만들기 위한 Step들을 연결하는것
- 재사용이 가능한 컴포넌트
- 개인이 만든것을 사용해도 좋고, 공용 Action을 사용할수도있다.

### Runner

- Github action runner 어플리케이션이 설치된 머신으로, Workflow가 실행될 인스턴스

---

## Github Action 순서

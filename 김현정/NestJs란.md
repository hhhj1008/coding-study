## 📌 1. NestJS란?

효율적이고 확장 가능한 Node.js의 서버 사이드 애플리케이션을 구축하기 위한 프레임워크로, progressive JavaScript를 사용하고 TypeScript로 구현하는 것을 지원하며(순수 JavaScript 만으로도 개발이 가능) , OPP(객체 지향 프로그래밍), FP(기능 프로그래밍) 및 FRP(기능 프로그래밍)의 요소들이 포함되어 있다.


>서버 사이드 <br>
: 네트워크의 한 방식인 클라이언트-서버 구조의 서버 쪽에서 행해지는 처리를 뜻한다. <br>
progressive <br>
: 웹과 네이티브 앱의 이점을 모두 수용하고 표준 패턴을 사용해 개발 된 것을 뜻한다.

<br>


## 📌 2. NestJS를 사용하는 이유
### 2-1. 사용하기가 쉽다
기존의 NodeJs + Express 개발에서는 초기 설정이 번거로웠지만, NestJS에서는 cli를 전역적으로 설치한 후 nest 명령어를 통해 프로젝트를 만들어 컨트롤러, 서비스, 모듈 테스트 파일 등을 사전에 설정된 상태로 시작할 수 있다.

### 2-2. 아키텍처가 정의되어 있다
NestJs의 공식문서의 Philosophy를 보면 "Nest provides an out-of-the-box application architecture which allows developers and teams to create highly testable, scalable, loosely coupled, and easily maintainable applications." 라고 적혀있다.

이는 Nest는 개발자와 팀이 높은 테스트 가능성과 확장이 가능한 느슨하게 결합된 유지 관리가 쉬운 애플리케이션을 만드는 즉시 사용 가능한 애플리케이션 아키텍처를 제공한다로 해석할 수 있는데, 기존 Node.js에서 제공되지 않던 아키텍처를 제공하여 개발의 생산성과 유지 보수 성이 향상될 수 있다는 점이다.

> 아키텍처가 필요한 이유?
특정한 프로젝트를 진행할 때 만약 혼자서 진행을 한다고 하면 자신만의 프로그래밍 성격에 맞게 진행을 해도 무방하다. 하지만 나중에 유지 보수성을 생각하여 구조 및 패턴을 정해둔다면 유지 보수도 쉬워질 뿐만 아니라 개발을 할 때도 생산성이 향상된다.

<br>

## 3. NestJs 초기설정
### 3-1. NestJs 설치
아래의 명령어를 실행
```shell
npm i -g @nestjs/cli
```
### 3-2. NestJS 프로젝트 생성
아래의 명령어를 통해 NestJS 프로젝트를 생성할 수 있다.
(project-name에는 생성하고자 하는 프로젝트의 이름을 적어주어야 한다.)
```shell
nest new project-name
```
실행을 하면 어떤 패키지 매니저를 사용할 것인지 선택창이 나온다.
방향키와 엔터키를 통해서 설정할 수 있다. (본인은 npm을 선택)

![image](https://user-images.githubusercontent.com/110225060/198237485-2dcbb514-5ee1-4bd6-a7e8-2f93f1df90b9.png)

- `npm` : Node Packaged Manager의 약자로 말 그대로 node 패키지를 관리하는 툴
- `yarn` : 의존성관리 javascript 패키지 매니저로 java에 gradle , php의 composer 와 같은 역할을 한다.
- `pnpm` : pnpm은 performant npm의 약자로, npm보다 낫고 yarn보다 빠른 패키지 매니저의 특징을 갖고 있다.
- 각 패키지 매니저의 자세한 내용은 👉[여기](https://yceffort.kr/2022/05/npm-vs-yarn-vs-pnpm)를 참조

![image](https://user-images.githubusercontent.com/110225060/198237945-77501e3e-ca15-4f6b-ab81-864daceee81c.png)


프로젝트가 성공적으로 생성되었을 때의 폴더 구조

### 3-3. contorller, service, module 폴더 및 파일 생성
생성된 프로젝트 디렉토리로 이동하여 아래의 명령어 실행
🔻contorller 폴더 및 파일 생성
```shell
nest g controller [contoller-name] --no-spec
```
![image](https://user-images.githubusercontent.com/110225060/198238097-d5b5166b-5b38-4cc2-9720-e2bb1677aff5.png)

controller 파일 및 폴더가 생성되었고, 생성된 controller가 app.module에 추가되었다는 로그가 뜬다면 성공적으로 생성된 것이다.

![image](https://user-images.githubusercontent.com/110225060/198238170-be5bb578-e7e4-48d5-8461-18dcdde8b0cd.png)

src 폴더에 폴더 및 파일이 추가된 것을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/110225060/198238221-ac3f63b5-ad64-4c12-810c-603df0ed5cdc.png)

app.module에도 생성된 컨트롤러가 추가되어 있다.

service와 module도 동일하게 아래의 명령어 실행

🔻service & module 
```shell
nest g service [service name] --no-spec
nest g module [module name]
```

> --no-spec 란? 
스펙파일을 생성하지 않는 다는 것으로, 스펙파일은 테스트를 위해 생성하는 파일이다.

### 3-4. 프로젝트 실행
```shell
npm run start
```

![image](https://user-images.githubusercontent.com/110225060/198238270-dc0fd877-bf9b-41b9-a0a1-758e1e8d9bb7.png)

성공적으로 실행되었을 경우의 콘솔 로그.
포트 번호는 main.ts에서 확인 및 설정이 가능하다.

<br>

---

#### 링크
📌[NestJS Docs](https://docs.nestjs.com/)
📌[Nest.js란 무엇인가 (번역)](https://sohyunsaurus.tistory.com/85)
📌[우리가 NestJS를 사용해야하는 이유](https://nemne.tistory.com/m/26)



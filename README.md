# TypeScript
타입스크립트 학습을 위한 저장소

# 타입스크립트 개발 환경 만들기
- scoop 프로그램 설치
  1. 윈도우 파워셸 실행 ```[시작] - [Window PowerShell]```
  2. 윈도우 파워셸에서 scoop 설치
     - 윈도우 실행 규칙 변경
     ```[Set-ExecutionPolicy RemoteSigned -scope CurrentUser] -> [A]```
     - 앞으로 scoop을 이용해 설치하는 모든 프로그램의 경로 설정
     ```[#env:SCOOP='C:\Scoop]'```
     - scoop을 설치
     ```[Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')]```
     - scoop을 이용해 aria2를 설치 -> scoop이 다중 내려받기를 할 수 있게 되어 프로그램 설치 시간이 단축됨
     ```[scoop install aria2]```
     - git을 설치하면 scoop은 다양한 설치 관련 정보를 깃허브에서 얻는다.
     ```[scoop install git]```
  3. 환경변수 설정
     - ```[Window - 시스템 환경 변수 편집] - [새 사용자 변수] - [변수이름 : Scoop, 변수 값 : c:\scoop] - [확인]```
- nodejs 설치
  1. 윈도우 파워셸 ```[scoop install nodejs-lts] - [node -v]```
- 구글 크롬 브라우저 설치
  1. 윈도우 파워셸 ```[scoop install googlechrome] - [chrome]```
- 타입스크립트 컴파일러 설치
  1. 프로젝트 디렉토리의 터미널에 다음 명령어를 입력해 typescript 패키지를 설치한다. 타입스크립트는 nodejs 환경에서만 동작하며 따라서 scoop이 아닌 Node.js의 패키지 관리자인 npm을 사용하여 -g 키워드를 통해 전역에 설치한다.
  ```[npm i -g typescript]```
  2. 설치된 컴파일러의 버전 확인
  ```[tsc --version]```
- touch 설치 
  1. 파워셸에서 touch 프로그램 설치
  ```[scoop install touch]```
  2. 프로젝트 디렉토리의 터미널에서 touch 명렁으로 파일을 생성한다.
  ```[touch hello.ts]```
- 타입스크립트 컴파일과 실행
  1. hello.ts에 ```[console.log("Hello World!");]``` 를 입력하고 저장
  2. 터미널에서 명령 실행 -> hello.js 파일 생성됨
  ```[tsc hello.ts]```
  - 즉 타입스크립트 소스가 TSC에 의해 트랜스파일되어 hello.js 파일이 생성됨
  3. Node.js로 hello.js 파일 실행 -> Hello World! 출력됨
  ```[node hello.js]```
- ts-node 설치
  1. 타입스크립트 코드를 ES5로 변환하고 실행까지 동시에 하기 위해 ts-node 프로그램 설치
  ```[npm i -g ts-node] - [ts-node -v]```
  2. 해당 파일이 있는 폴더에서 다음 명령으로 컴파일과 실행 동시에 진행 -> hello.js 파일을 삭제하더라도 Hello World! 가 출력됨
  ```[ts-node hello.ts]```

# 타입스크립트 프로젝트 생성 및 관리
- 타입스크립트 개발은 Node.js 프로젝트를 만든 다음 개발 언어를 타입스크립트로 설정하는 방식으로 진행한다.
- 프로젝트는 디렉토리를 하나 만들고 여기에 package.json이란 이름의 파일을 만드는 것으로 시작한다.
- 보통 package.json은 터미널에서 ```npm init``` 명령을 실행해 생성한다.
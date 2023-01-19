# TypeScript
타입스크립트 학습을 위한 저장소

# 타입스크립트 개발 환경 만들기
- scoop 프로그램 설치
  1. 윈도우 파워셸 실행 ```[시작] - [Window PowerShell]```
  2. scoop 설치
     - 윈도우 실행 규칙 변경
     ```[Set-ExecutionPolicy RemoteSigned -scope CurrentUser] - [A]```
     - 앞으로 scoop을 이용해 설치하는 모든 프로그램의 경로 설정
     ```#env:SCOOP='C:\Scoop'```
     - scoop을 설치
     ```Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')```
     - scoop을 이용해 aria2를 설치 -> scoop이 다중 내려받기를 할 수 있게 되어 프로그램 설치 시간이 단축됨
     ```scoop install aria2```
     - git을 설치하면 scoop은 다양한 설치 관련 정보를 깃허브에서 얻는다.
     ```scoop install git```
  3. 환경변수 설정
     - ```[Window - 시스템 환경 변수 편집] - [새 사용자 변수] - [변수이름 : Scoop, 변수 값 : c:\scoop] - [확인]```

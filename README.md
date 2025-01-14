# K-shield.jr
>[케이쉴드주니어 10기 모의해킹 A반 4조]
<br>

## API 취약점을 활용한 시나리오기반 WordPress 환경 모의해킹 보고서

<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=K-shield.jr&fontSize=90" />
<br>

## 1.1 모의해킹 목적
>웹 모의해킹을 통해 WordPress를 이용하여 만들어진 웹 서비스에 존재하는 보안 위협을 사전에 발견 및 조치하여 자산의 보안성과 안정성을 확보한다.

## 1.2 수행 및 인원
>본 모의해킹은 2023.05.01 부터 2023.05.21까지 약 3주간 진행되며, 총 5명이 투입된다. 자세한 일정은 아래 표 1-1과 같다. 
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/8571787c-40fd-45d6-b3c0-040bc02bbcf4)
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/1d186aa6-a15a-4154-af50-8bf3b13b3644)

## 1.3 수행대상
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/d6897ff8-f668-499d-850c-28e3ba7957f2)

## 1.4 수행 단계
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/724bd09a-91b1-4681-9d09-e2f462afad05)

## 1.5 취약점 점검 항목
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/9bb58fd7-581a-4350-b70b-1563a36c57d3)

## 1.6 모의해킹 수행 시나리오

## 1.6.1 웹 서비스 관리자 권한 획득

>1.낮은 권한의 계정으로 로그인 수행
>2.IN-001 취약점을 이용한 피싱 페이지 생성
>3.피싱 페이지에 관리자 권한 가진 사용자 접근 시 관리자 권한을 가진 새로운 사용자 계정 생성
>4.내부 관리자 권한 획득으로 사용자 정보 등 주요 정보 열람 및 변조 가능


## 1.6.2 외부 비인가자 입장에서 웹 서버 권한 탈취
>1.프로세스 검증 누락 취약점(PV-001)을 통해 서버 관리자 로그인 인증 우회
>2.파일 업로드 취약점(FU-001)을 통한 웹 셀 업로드
>3.웹 셀 파일 접근을 통한 내부 서버 침투
>4.리버스 쉘 환경에서 TTY 세션 생성 후 root 권한 상승
>5.uid, gid가 0인 계정 생성으로 지속적인 정보 탈취 및 변조

## 1.7 점검 도구 
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/59415cdb-3f8f-45d4-9692-3d41bd970c65)

# 2. 취약점 분석

## 2.1.1 서비스 별 취약점 
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/bbca8317-5533-486c-b223-f70379bf20ec)

## 2.1.2 총평
>대상 사이트 취약점 분석 결과 SQL 인젝션 3건, 디렉터리 인덱싱 2건, 크로스사이트 스크립팅 4건, 불충분한 인가 2건, 프로세스 검증 누락 1건, 파일 업로드 1건, 파일 다운로드 1건이 발견되었다.

## 2.2 전체 환경 분석
>아래 표 2-2는 4.7.x 버전의 워드프레스에 설치된 플러그인이다.
![image](https://github.com/nyang-code/K-shield.jr/assets/85928740/824128e9-0b94-4fd3-8969-c43bf20e63d5)

## 2.3 취약점 분석 상세 내역은 아래 pdf로 확인할 수 있다.

[[결과보고서]A반_A_04조.pdf](https://github.com/user-attachments/files/15936736/A._A_04.pdf)

>발표 ppt -> [A04 모의해킹 ppt_최종본.pptx](https://github.com/user-attachments/files/15936742/A04.ppt_.pptx)



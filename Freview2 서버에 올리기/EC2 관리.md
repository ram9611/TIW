# EC2 관리
### 24.12.10
> EC2 인스턴스 생성
>> OS : ubuntu <br>
>> 인바운드 : SSH, HTTP 모두 접근 설정 <br>
>> 스토리지 : 30GiB, gps 설정 <br>
>
> ![image](https://github.com/user-attachments/assets/25f45111-8861-4459-a619-749d1d62e283)

### 24.12.15
> EC2 인스턴스 탄력적 IP 부여 <br>
> 인스턴스에 java17, tomcat9.0.98 설치 완료 <br>
> Freview2 프로젝트 빌드 후 배포 시도했으나 Maven WAR 플러그인(maven-war-plugin) 버전이 오래되어, 현재 사용 중인 Java 버전 또는 Maven 버전과 호환되지 않아 실패
>> ![image](https://github.com/user-attachments/assets/53a181e1-ea77-4ee7-a102-ff4299328995)
>> 깃허브 프로젝트와 로컬 내용 동기화하는 작업 진행 <br>
>> 배포 작업을 위한 리팩토링 브랜치 생성
>

### 24.12.20
> 리팩토링 브랜치에서 Maven war plugin 추가 후 main 브랜치로 머지 <br>
> ec2 인스턴스로 clone하고 war파일 만들기 성공 <br>
> war 파일 tomcat/webapps 파일에 복사하고 tomcat 재시작하려고 하였으나, tomcat이 ubuntu에 서비스로 등록되어 있지 않음 <br>
> 패키지 매니저 사용대신 tomcat 공식 웹사이트에서 압축을 풀고 다운로드하여 설치되지 않은 것으로 확인 <br>

### 25.01.04
> 8080 접속하니 tomcat 접속안되는 이슈 발생 <br>
> 기존 톰캣 지우고 재설치 후 접속 확인 <br>
> tomcat9.service 파일 생성 <br>
> > ![image](https://github.com/user-attachments/assets/0cd74578-d12f-45c4-90df-4ba3c8a8e366)
>
> tomcat 서비스 실행할 전용 사용자와 그룹 생성
> > ![image](https://github.com/user-attachments/assets/48addeb6-e234-4e11-b56e-019ec61a64e9)
>
> Tomcat 디렉토리 소유권 변경 및 권한 설정
> >![image](https://github.com/user-attachments/assets/721bc4b1-6a28-4ffd-acb1-9d393ba0ea3a)
>
> Tomcat 서비스 등록 확인
> >![image](https://github.com/user-attachments/assets/28e64ac8-bbb6-427a-9862-b0f8ad2d7a75)

### 25.01.30
> FReview2를 톰캣에 배포하였으나 url 접속시 404에러 발생 <br>
> tomcat 지우고 다시 설치 <br>
> 배포까지 하고 catalina.out에서 오류 확인하며 진행 필요 <br>



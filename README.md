# secureQR-web-client Test Application


### 1. Description 
- 앞서 개발한 `secureQR-module` 라이브러리를 적용한 웹 클라이언트 적용 예시
- 암호화된 QR 코드를 생성하고 발급하는 역할을 수행하는 예시

<br/>

### 2. 개발 환경
 &nbsp;개발 언어 : ![JAVA11](http://img.shields.io/badge/-Java11-006cb7?style=flat&logo=Java) & ![JAVA](http://img.shields.io/badge/-Javascript-006cb7?style=flat&logo=Javascript)<br/>
  &nbsp;개발 환경 :  ![Springboot](http://img.shields.io/badge/-Springboot2.5.4-000000?style=flat&logo=springboot) & ![Springboot](http://img.shields.io/badge/-Gradle7.1.1-006cb7?style=flat&logo=gradle)


<br/>

### 3. 실행 방법

- 로컬에서 실행하는 경우

  1. 동봉한 jar 파일을 다운로드 받음.

  2. cmd 나 터미널을 실행

  3. 해당 jar파일 디렉토리로 이동

  4. 다음과 명령어를 입력 

     ``` sh
     java -jar secureQR-0.0.1-SNAPSHOT.jar
     ```

  5. 웹 브라우저에 localhost:8080/ 을 입력

  6. 아래의 화면처럼 정보들을 입력
     
     ![home](https://user-images.githubusercontent.com/48395704/132034582-11c36a78-79ae-40e9-8f3d-e806115c6237.gif)
     
  7. 실행 결과 확인 
     ![클라3](https://user-images.githubusercontent.com/54317409/138597387-1ba5f753-3348-4676-8ad4-c2cbabc81885.gif)






### 4. 전체적인 설계흐름
- 먼저 해당 레파지토리는 `Sotree17/secure-module`를 라이브러리화 한 jar파일을 사용 
- `Sotree17/secure-server-example`의 결과물을 REST API 서버 역할로 둠
- 해당 서버에 요청함으로써 암호화된 QR 이미지를 사용자에게 보여주는 흐름을 갖음. 

#####   &nbsp;&nbsp; 암호화된 secureQR 이미지 생성 과정 
- REST API 서버의 API `/generator` 에 대한 POST 요청을 통해 이루어짐 
<p align="center"><img height="60%" width="70%" alt="텍스트 정보제공" src="https://user-images.githubusercontent.com/54317409/132015823-f53589db-a641-4cbc-9f13-ae636d502e62.PNG"></p>

(1) 사용자가 입력한 데이터를 기반으로 암호화 QR 생성 요청 <br/>
(2) 암호화 REST API 서버에서의 인터페이스 구현체 호출 <br/>
(3) 암호화 QR 라이브러리 Geneator 클래스의 createSecureQRcode() 호출 <br/>
(3) 암호화 QR 이미지 생성하게됨. <br/>
(4) 클라이언트에게 `암호화 QR 이미지` byte[] 반환 <br/>
 

#####   &nbsp;&nbsp;응답받은 secureQR 이미지 반환 과정
- 다음의 설계 흐름을 통해 사용자에게 SecureQR 이미지를 보여줌 
<p align="center"><img height="60%" width="70%" alt="텍스트 정보제공" src="https://user-images.githubusercontent.com/54317409/132016161-6ae74c63-287e-4a60-b0e5-c03af4ebd88a.png"></p>

(1) 응답으로 부터 byte[] 정보 추출 <br/>
(2) 이미지 파일 저장 경로 설정 <br/>
(3) 이미지 파일 생성 후 화면에 암호화된 QR 출력 <br/>



## Dependency License Report
_2021-10-21 21:04:04 KST_
### Apache License, Version 2.0

**1** **Group:** `org.apache.httpcomponents` **Name:** `httpclient` **Version:** `4.5.13` 
> - **POM Project URL**: [http://hc.apache.org/httpcomponents-client](http://hc.apache.org/httpcomponents-client)
> - **POM License**: Apache License, Version 2.0 - [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)
> - **Embedded license files**: [httpclient-4.5.13.jar/META-INF/LICENSE](httpclient-4.5.13.jar/META-INF/LICENSE) 
    - [httpclient-4.5.13.jar/META-INF/NOTICE](httpclient-4.5.13.jar/META-INF/NOTICE)

**2** **Group:** `org.springframework.boot` **Name:** `spring-boot-devtools` **Version:** `2.5.4` 
> - **POM Project URL**: [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)
> - **POM License**: Apache License, Version 2.0 - [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)
> - **Embedded license files**: [spring-boot-devtools-2.5.4.jar/META-INF/LICENSE.txt](spring-boot-devtools-2.5.4.jar/META-INF/LICENSE.txt) 
    - [spring-boot-devtools-2.5.4.jar/META-INF/NOTICE.txt](spring-boot-devtools-2.5.4.jar/META-INF/NOTICE.txt)

**3** **Group:** `org.springframework.boot` **Name:** `spring-boot-starter-thymeleaf` **Version:** `2.5.4` 
> - **POM Project URL**: [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)
> - **POM License**: Apache License, Version 2.0 - [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)
> - **Embedded license files**: [spring-boot-starter-thymeleaf-2.5.4.jar/META-INF/LICENSE.txt](spring-boot-starter-thymeleaf-2.5.4.jar/META-INF/LICENSE.txt) 
    - [spring-boot-starter-thymeleaf-2.5.4.jar/META-INF/NOTICE.txt](spring-boot-starter-thymeleaf-2.5.4.jar/META-INF/NOTICE.txt)

**4** **Group:** `org.springframework.boot` **Name:** `spring-boot-starter-web` **Version:** `2.5.4` 
> - **POM Project URL**: [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)
> - **POM License**: Apache License, Version 2.0 - [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)
> - **Embedded license files**: [spring-boot-starter-web-2.5.4.jar/META-INF/LICENSE.txt](spring-boot-starter-web-2.5.4.jar/META-INF/LICENSE.txt) 
    - [spring-boot-starter-web-2.5.4.jar/META-INF/NOTICE.txt](spring-boot-starter-web-2.5.4.jar/META-INF/NOTICE.txt)

### MIT License 
**1** **Name** `BootStrap` **Version:** 4.0.0-beta
> - **POM License** [https://github.com/twbs/bootstrap/blob/c767a00d5d0b0511400fc8bce63edd6fcf589b27/LICENSE](https://github.com/twbs/bootstrap/blob/c767a00d5d0b0511400fc8bce63edd6fcf589b27/LICENSE)

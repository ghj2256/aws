# wildrydes-site

## 개요
지도에 자신의 위치를 표시하면 해당위치로 차량을 호출하는 서비스를 제작했다. 서비스에서 제공하는 기능은 회원가입, 가입인증, 로그인, 차량호출 기능이다. 사용자의 위치를 나타내기 위에 HTML 기반 인터페이스를 제공한다. RESTful API를 이용해 사용자의 차량 호출 요청을 전달하고, 임의의 차량을 응답한다. 위 서비스를 제공하기 위해 회원가입과 가입인증 절차, 로그인 기능을 구현했다. 이 프로젝트는 AWS 서버리스 가이드 프로젝트를 참고하여 제작하였다.

## 사용한 AWS 서비스
* Lambda
*	API Gateway
*	DynamoDB
*	IAM
*	Amplify
*	Cognito
*	CodeCommit

## 아키텍처 구조
![image](https://user-images.githubusercontent.com/46516796/103148285-608b9800-47a1-11eb-8520-d01d6458c51f.png)   
1. 정적 웹 호스팅   
HTML, CSS, JavaScript, 이미지 파일 등 사용자의 웹 브라우저에서 작동하는 리소스들을 Amplify를 이용해 정적 웹 리소스 호스팅을 한다.
2. 사용자 관리   
Cognito를 사용해 인증기능과 사용자 관리기능으로 백엔드 API를 보호한다.
3. 서버리스 백엔드   
DynamoDB로 API의 Lambda 함수가 데이터를 저장할 수 있는 공간을 제공한다.
4. RESTful API   
브라우저에서 실행되는 JavaScript는 Lambda 및 API Gateway를 사용하여 백엔드 API로부터 데이터를 송수신한다.

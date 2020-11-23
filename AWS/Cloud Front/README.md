
-eb 앱 생성


-route53 도메인 등록



-ec2 로드밸랜서 등록

1. 새로드 밸런서 선택 후 Http/Https 생성

2.가용영역 4개 다 선택 후 다음

3. example-target 생성 후 해당 환경을 항목에 추가


cloudfront

1. Create Distribution => web 선택

2. Origin Domain Name에 해당 로드 밸랜서 선택

3. Viewr Protocol Policy 에서 Redirect 선택

4. SSL Certificate에서 커스텀 선택하고 Request 버튼 누름

5. 도메인 이름에 www.example.com과 example.com을 입력

6. DNS 검증을 누르고 해당 도메인 클릭후 Route 53에서 레코드 생성 선택 

7. CloudFront 탭으로 다시 이동해서 새로고침

8. CName에 www.example.com을 입력하고 아까 발급받은 인증서 올림

9. 만들어진 것 선택하고 general에서 edit 클릭후 cname에 example.com도 추가

10. Route53로 이동 후 호스팅 영역 레코드에서 기존의 A 2개를 삭제 후 cloudfront 선택
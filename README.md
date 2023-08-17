# serverless-regist-with-cognito
API Gateway Authentication using Cognito

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/e430391d-3428-4d17-9b7c-10973bd3e4af)

1. 사용자가 API 접근하면 해당 API는 Cognito에 가서 Authenticate와 token에 대한 정보를 받아 옴
2. Token을 사용해 AWS Credentials로 변환한다.
3. 변환 된 Credentials을 사용하여 AWS에 Access한다.

### Create Cognito User Pool
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/1c6cbf60-e7ac-4498-9355-0166166fa185)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/5e8b2b7f-34c6-481c-a8ba-76368eb77251)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c5460ded-fd3c-43a1-9944-5f4d0f92a2c3)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c0aef501-b78a-44fb-aee1-b44f273914e0)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/d862dd7d-a272-4aca-9e67-9a938867aa85)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/6a0d7ea7-0663-4b09-9c70-baace1d33a6e)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/46c49d88-04d7-4826-991b-d7d6fd9cdec4)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/bb42fb4e-26de-4b8e-a014-916fe3a7bd8a)

Cognito를 생성

### Setting API Gateway
API에서 REST API 사용시 Cognito를 사용하여 사용자 인증이 가능하도록 구성

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/91f2ecfa-05ae-422a-8330-3f881f8ff4a6)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/4de46e8c-8577-4010-90cd-c4cbed361f6b)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/ec6df31a-3345-4190-9e49-08ad54afd03f)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/de198f5b-467f-4475-8ef0-eea1524290e0)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/a5574da7-5ba1-4b15-9580-e4c741bb9a2e)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/eec14f18-d40c-46f0-b395-4e9e7d74a492)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/638c0631-cf2b-476a-b3fd-ff4dbec5fb9a)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/1a66af37-191e-4ffe-a735-54fad733e480)

Domain에  reponse_type이 token인 것을 알 수 있다.

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/38c06479-9f8e-4934-9642-28c0dd25b6e5)

Sign Up을 눌러 회원가입

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/41d5971d-8677-49b4-83d5-63d2dcfbaec7)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/60015818-33d1-4f8f-a0ee-d98410323def)

자신의 이메일로 이동해서 아래와 같은 E-mail이 왔는지 확인

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/8113008b-f803-436c-91d9-569474917b3f)

코드를 기억하고 아래와 같이 입력

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/4cfd5fe7-e454-4d16-aab6-e770154bf856)

가입한 유저로 로그인

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c29f74cd-25fb-4052-afcf-58b95a59f35c)

token이 생성 됨

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/21dfe1fa-c6a9-414a-8416-6bb339381f9a)

Token을 복사 후 API Gateway에서 확인

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/5482bd75-88f2-4d0a-a028-90db426e62d0)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/80a99a03-60e2-4bbe-a5bd-4430b4ee6066)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/17f78d4f-b65d-4227-bd13-0eb3efc19638)

### Authorizer API
API Gateway에 Access하면 Cognito인증을 통해서만 접근이 가능하도록 구성

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/adf8ab33-5044-48dd-ba56-fbb909f8bfe7)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c018e53f-5a00-48d2-8b3f-3e2edbd8c4df)

배포를 하고 접근해보면 API가 Unauthorized라는 오류를 반환

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/195a5491-25a4-4190-b10d-dd7d9e04da1e)

Header에 auth라는 key에 token 값을 넣어주면 아래와 같이 정상 적으로 접근이 됨

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/06b252c5-91ec-4f83-aadd-9667bc31e78e)

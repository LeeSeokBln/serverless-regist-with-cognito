# serverless-regist-with-cognito
API Gateway Authentication using Cognito

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/e430391d-3428-4d17-9b7c-10973bd3e4af)

1. 사용자가 API 접근하면 해당 API는 Cognito에 가서 Authenticate와 token에 대한 정보를 받아 옴
2. Token을 사용해 AWS Credentials로 변환한다.
3. 변환 된 Credentials을 사용하여 AWS에 Access한다.

### Create Cognito User Pool
![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/e8f5a86c-0c61-45aa-bc60-ffe24b539818)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/40c0652f-8066-460e-bf7b-e33ab6151596)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/1056801d-6405-423f-b571-c79a426f8c17)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/5d9f333e-bca4-421a-a6e2-4d2a45a357f5)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/5c1b225a-6ae3-4cd8-bbfc-1e7280166add)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/23922e56-13bd-4ae2-bca0-bbd1496337be)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/22bb34fa-7845-42e5-9bfd-bfe64cb0fab3)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/38e5215b-3a67-40b1-b6ef-db84d9c352cb)

Cognito를 생성

### Setting API Gateway
API에서 REST API 사용시 Cognito를 사용하여 사용자 인증이 가능하도록 구성

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/cdeca288-c32d-493f-b618-20234b08a27c)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/ae5357a0-e74a-42f3-81bd-78db34d0ee38)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/60db428c-e46e-49b6-b900-c4a2d021b157)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/313c3376-db8f-482a-a65e-cd7d861a3960)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/76af2be5-d836-4af0-987a-2e3ef5c9fdb1)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/b453aa75-5941-4d91-87d1-ab13b1192657)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/be6cca5e-843d-41c3-abc9-7e11723d18d8)

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/2e9eb6de-29aa-4cd3-97e9-507193201b70)


Domain에  reponse_type이 token인 것을 알 수 있다.

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/d620f6c9-03f3-45ea-98c2-04959e803cb9)

Sign Up을 눌러 회원가입

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/41d5971d-8677-49b4-83d5-63d2dcfbaec7)
![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/60015818-33d1-4f8f-a0ee-d98410323def)

자신의 이메일로 이동해서 아래와 같은 E-mail이 왔는지 확인

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/8113008b-f803-436c-91d9-569474917b3f)

코드를 기억하고 아래와 같이 입력

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/89f2bcce-e39b-4fc6-984a-2ec18d14aa0f)


가입한 유저로 로그인

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c29f74cd-25fb-4052-afcf-58b95a59f35c)

token이 생성 됨

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/21dfe1fa-c6a9-414a-8416-6bb339381f9a)

Token을 복사 후 API Gateway에서 확인

![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/c2c005ee-0ca1-4b80-8fea-460fa594dbf7)

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/17f78d4f-b65d-4227-bd13-0eb3efc19638)

### Authorizer API
API Gateway에 Access하면 Cognito인증을 통해서만 접근이 가능하도록 구성

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/adf8ab33-5044-48dd-ba56-fbb909f8bfe7)
![image](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/36889723-f11e-457d-b629-4a7b807c3871)


배포를 하고 접근해보면 API가 Unauthorized라는 오류를 반환

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/195a5491-25a4-4190-b10d-dd7d9e04da1e)

Header에 auth라는 key에 token 값을 넣어주면 아래와 같이 정상 적으로 접근이 됨

![Untitled](https://github.com/LeeSeokBln/serverless-regist-with-cognito/assets/101256150/06b252c5-91ec-4f83-aadd-9667bc31e78e)

# Training

패킷 인젝션 트레이닝은 **실제 서비스 중인 사이트가 아닌**, 모의해킹 목적으로 호스팅 중인 **온라인 데모 서버**에서 실습을 진행할 예정이다.

---

## 주의 사항

- 실제 서비스 중인 사이트에서 해킹을 시도할 경우, 법적인 문제가 발생할 수 있으므로 반드시 금지한다.
- 반드시 허가된 테스트 환경 또는 모의해킹용 데모 사이트에서만 실습해야 한다.

---

## 실습 사이트

대표적인 온라인 데모 사이트는 **OWASP Juice Shop**이다.

- **OWASP Juice Shop 온라인 데모**:  
  [https://juice-shop.herokuapp.com/#/](https://juice-shop.herokuapp.com/#/)

이 사이트에서 다양한 웹 취약점과 함께 패킷 인젝션 실습을 진행할 예정이다.


<img width="1902" height="944" alt="image" src="https://github.com/user-attachments/assets/6dd68231-13ca-4840-9c08-4d437acddce0" />

---

## 실습

### step 1. 브라우저 오픈

Proxy -> Intercept -> Open browser

<img width="1093" height="814" alt="image" src="https://github.com/user-attachments/assets/a4a64e16-cfd3-4462-a44f-5707c496f842" />

### step 2. 페이지 열기

<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/bfccf1c1-5bad-45d9-bc3f-a336f7fa4664" />

### step 3. 패킷 인터렉션

#### 시나리오 - 회원가입 화면에서 요구하는 규칙을 지켜지지 않은 데이터로 회원가입을 진행한다.

비밀번호는 반드시 5-40 자 이상이어야 한다는 규칙이 있기에 화면에서는 5자리 이상을 입력하고 패킷 인터렉션을 통해 4자리로 변경해 보겠다.
<img width="498" height="674" alt="image" src="https://github.com/user-attachments/assets/8277d2b6-dbf5-4eca-9e8b-c778edd4bfd4" />

먼저 **Intercept on** 을 활성화 해야 Request 및 Reponse를 가로챌 수 있다.
<img width="1103" height="825" alt="image" src="https://github.com/user-attachments/assets/5d7f441c-3f41-47f6-888e-2d914b18a4bd" />

<img width="492" height="676" alt="image" src="https://github.com/user-attachments/assets/b98ac83d-3910-4e02-8909-88d45f90a87f" />

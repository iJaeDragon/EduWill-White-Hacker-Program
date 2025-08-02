# Training - Burp Sutie

브루트 포스 트레이닝은 **실제 서비스 중인 사이트가 아닌**, 모의해킹 목적으로 호스팅 중인 **온라인 데모 서버**에서 실습을 진행할 예정이다.

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

### step 3. 브루트 포스

#### 시나리오 
 - 타겟의 아이디는 알고 있지만 비밀번호를 모르는 상태
 - 다양한 패스워드로 로그인을 시도하여 타겟의 비밀번호 파악
 - 파악한 계정 정보로 로그인 진행

##### Intercept On 활성화

<img width="1096" height="814" alt="image" src="https://github.com/user-attachments/assets/d79708e7-9c48-400e-97bb-994915e08f83" />

##### 로그인 요청 시 서버로 전송되는 데이터를 확인하기 위해 임의 값으로 로그인을 시도한다.

<img width="488" height="564" alt="image" src="https://github.com/user-attachments/assets/7b3ffff3-891b-43d4-b5a6-47ada74fe5f8" />

##### 전달하려는 요청을 확인하고 Send to Intruder 클릭

<img width="1091" height="818" alt="image" src="https://github.com/user-attachments/assets/1dfcdd2e-8dcc-48c0-8dda-269ef1c7a900" />

##### 파라미터를 분석하여 대입할 항목을 찾아 payload position을 추가한다.

<img width="626" height="502" alt="image" src="https://github.com/user-attachments/assets/1fb8b88c-6075-4b07-bcbf-e5276a0cf48f" />

##### Payload configuration에 시도할 패스워드 목록을 입력한다.

(시도할 패스워드 목록)

```

  qwer1234
  1q2w3e4r
  11111
  22222
  123
  1234
  123456

```

<img width="1095" height="814" alt="image" src="https://github.com/user-attachments/assets/4d401a9d-c525-4d3a-bdf4-65a2006a33be" />


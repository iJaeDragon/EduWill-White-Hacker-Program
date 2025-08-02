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

## 🧪 실습: Burp Suite를 이용한 Brute Force

---

### ✅ Step 1. Burp 브라우저 실행

- Burp Suite에서 `Proxy → Intercept → Open Browser` 클릭  
<img width="600" alt="open-browser" src="https://github.com/user-attachments/assets/a4a64e16-cfd3-4462-a44f-5707c496f842" />

---

### ✅ Step 2. 대상 페이지 접속

- Burp 브라우저에서 **OWASP Juice Shop** 사이트 접속  
<img width="100%" alt="open-page" src="https://github.com/user-attachments/assets/bfccf1c1-5bad-45d9-bc3f-a336f7fa4664" />

---

### ✅ Step 3. Brute Force 수행

#### 🔍 시나리오

- 타겟 계정의 **아이디는 알고 있음**
- 다양한 패스워드를 이용해 로그인을 반복 시도
- 비밀번호를 알아낸 후 로그인 성공 확인

---

#### ① Intercept On 설정

- Burp Proxy에서 `Intercept is on` 상태 확인  
<img width="600" alt="intercept-on" src="https://github.com/user-attachments/assets/13331181-3bf7-42ce-9647-e9ae1e74b93a" />

---

#### ② 임의 로그인 시도

- 존재하는 사용자 ID와 임의의 비밀번호로 로그인  
<img width="300" alt="fake-login" src="https://github.com/user-attachments/assets/7b3ffff3-891b-43d4-b5a6-47ada74fe5f8" />

---

#### ③ 요청 캡처 및 Intruder로 전송

- 서버로 전송되는 로그인 요청을 Burp에서 확인하고  
  **[Send to Intruder]** 버튼 클릭  
<img width="600" alt="send-to-intruder" src="https://github.com/user-attachments/assets/1dfcdd2e-8dcc-48c0-8dda-269ef1c7a900" />

---

#### ④ Payload 위치 설정

- 비밀번호 입력 필드에 `§`를 삽입하여 공격 위치 설정  
<img width="400" alt="payload-position" src="https://github.com/user-attachments/assets/77bb5306-9dbf-4f01-ac11-3b630a5169ea" />

---

#### ⑤ Payload 구성

- 공격에 사용할 패스워드 목록을 입력

```
  qwer1234
  1q2w3e4r
  11111
  22222
  123
  1234
  123456
```
<img width="600" alt="payload-config" src="https://github.com/user-attachments/assets/ebbbd6b3-7d12-4537-af2d-b111b231c0b9" />

---

#### ⑥ 공격 실행 및 결과 분석
  **[Start Attack]** 클릭

  응답 길이, 상태 코드 등을 기반으로 성공 요청 확인

<img width="600" alt="attack-results" src="https://github.com/user-attachments/assets/2767068e-d349-4255-935c-0dc06451f003" />

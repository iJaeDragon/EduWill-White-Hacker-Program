# BURPSUTIE

## 🧰 Burp Suite에서의 브루트 포스 공격

**Burp Suite**는 웹 애플리케이션 보안 테스트에 널리 사용되는 통합 프록시 도구로, 특히 **Intruder 기능**을 통해 브루트 포스 공격을 효과적으로 수행할 수 있습니다.

### 🔍 주요 기능: Intruder

Burp Suite의 Intruder는 요청 내 특정 파라미터에 대해 **자동으로 값들을 반복 주입하며 요청을 전송**할 수 있는 기능입니다. 이를 활용하여 로그인 폼, 인증 토큰, 쿠폰 코드 등 다양한 취약점을 테스트할 수 있습니다.

### 🧪 사용 예시

1. **로그인 페이지 가로채기**
   - Proxy 탭에서 로그인 요청을 가로채고, Intruder로 전송

2. **Payload 위치 설정**
   - 아이디나 패스워드 위치에 **§ 기호**를 이용해 반복 삽입할 위치를 지정

3. **Payload 리스트 설정**
   - Common passwords 또는 사용자 정의 패스워드 리스트 삽입

4. **공격 실행**
   - "Start Attack" 클릭하여 요청 자동 반복

5. **응답 결과 분석**
   - 응답 길이/코드/내용 차이로 성공 여부 식별

### 📌 장점

- **GUI 기반**으로 사용자 친화적
- 응답 차이를 기반으로 **성공한 요청 탐지 가능**
- **Payload 조합** 및 **타이밍 제어** 등 다양한 설정 지원
- 다른 Burp 기능(Fuzzer, Repeater, Logger 등)과 연동 가능

### ⚠️ 주의사항

- **무료 버전(Burp Community)**에서는 Intruder 속도가 제한됨  
  → 대규모 브루트 포스에는 **Professional 버전**이 필요
- 공격 속도 조절 없이 사용할 경우 **차단 또는 IP 블랙리스트**에 오를 수 있음

---

> ✅ 참고: 단순한 브루트 포스 외에도 Burp의 Intruder는 타이밍 공격, 인증 우회, 쿠폰 코드 추측 등 다양한 테스트에 응용될 수 있습니다.


<img width="1099" height="816" alt="image" src="https://github.com/user-attachments/assets/93d34360-efdc-4a57-b7b9-bfb018ec3452" />

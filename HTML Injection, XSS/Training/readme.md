# 🧪 Training

## 🧱 DVWA (Damn Vulnerable Web Application)

- 트레이닝 환경은 DVWA 환경을 구축하여 진행했습니다.
- **DVWA**는 웹 애플리케이션의 취약점(예: HTML Injection, SQL Injection, XSS 등)을 실습할 수 있도록 설계된 **취약한 웹 애플리케이션 플랫폼**입니다.
- 보안 교육, 모의 해킹 실습, 취약점 분석 훈련 등에 널리 활용됩니다.

---

## 🐳 DVWA Docker 환경 구축

아래 명령어를 사용하여 **Docker**로 DVWA를 손쉽게 실행할 수 있습니다.
```
# 버프수트에서 8080 포트를 사용하고 있어서 8081로 설정함.
# 8080 포트 사용 시 인터셉트가 걸리지 않을 수 있음.
docker run -d -p 8081:80 --name dvwa vulnerables/web-dvwa 

# 종료
docker stop dvwa
```
- `-d`: 백그라운드 모드로 실행  
- `-p 8080:80`: 호스트의 포트 8080을 컨테이너의 포트 80에 매핑  
- `--name dvwa`: 컨테이너 이름을 `dvwa`로 지정  
- `vulnerables/web-dvwa`: DVWA 공식 Docker 이미지

> ✅ 실행 후 브라우저에서 `http://localhost:8080` 접속

---

<img width="1917" height="943" alt="image" src="https://github.com/user-attachments/assets/204c9320-f501-41ee-ab1b-eeaf48642727" />

## 

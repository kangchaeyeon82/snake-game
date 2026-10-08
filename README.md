# 🐍 포즈로 조종하는 뱀 게임

[Teachable Machine](https://teachablemachine.withgoogle.com/) 포즈 모델로 웹캠 앞에서 몸 동작(left / right / up / down)을 해서 조종하는 웹 뱀 게임입니다.

- 사용 모델: https://teachablemachine.withgoogle.com/models/jq28dBmP8/
- 방향키로도 조작할 수 있습니다.

## 실행 방법

웹캠은 `https` 또는 `localhost`에서만 동작하므로 로컬 서버로 실행하세요.

```bash
python -m http.server 8000
```

브라우저에서 http://localhost:8000 접속 → **📷 웹캠 시작** → 카메라 허용 → **▶ 게임 시작**

## 설정

- **인식 기준**: 클래스 확률이 이 값 이상일 때만 방향을 바꿉니다.
- **속도**: 뱀이 움직이는 간격(ms)입니다.
- **카메라**: 카메라가 여러 개면 여기서 고릅니다.

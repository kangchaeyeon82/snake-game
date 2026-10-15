# 🐍 포즈로 조종하는 웹 게임

[Teachable Machine](https://teachablemachine.withgoogle.com/) 포즈 모델로 웹캠 앞에서 몸 동작(left / right / up / down)을 해서 조종하는 웹 게임 모음입니다. 방향키로도 조작할 수 있습니다.

| 파일 | 게임 |
|---|---|
| `index.html` | 🐍 포즈 뱀 게임 |
| `dodge.html` | ☄️ 운석 피하기 & 별 줍기: 우주선을 움직여 ⭐을 모으고 운석을 피합니다 (목숨 3개) |

## 연결된 외부 도구

| 도구 | 용도 | 주소 |
|---|---|---|
| Google Teachable Machine | 학습된 포즈 모델 (`model.json`, `metadata.json`) 불러오기 | https://teachablemachine.withgoogle.com/models/jq28dBmP8/ |
| TensorFlow.js `1.3.1` | 모델 실행 엔진 | https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@1.3.1/dist/tf.min.js |
| Teachable Machine Pose 라이브러리 `0.8` | 웹캠 처리, 포즈 추정, 관절/뼈대 그리기 | https://cdn.jsdelivr.net/npm/@teachablemachine/pose@0.8/dist/teachablemachine-pose.min.js |
| jsDelivr CDN | 위 라이브러리 배포 | https://www.jsdelivr.com/ |

브라우저 기능:

- **웹캠** (`getUserMedia`): 포즈 인식용 카메라 입력. 영상은 브라우저 안에서만 처리되고 서버로 전송되지 않습니다.
- **localStorage**: 최고 점수 저장 (`snakeBest`, `dodgeBest`)

> 라이브러리와 모델을 인터넷에서 불러오므로 실행할 때 인터넷 연결이 필요합니다.
> 모델을 바꾸려면 각 HTML 파일의 `MODEL_URL` 값을 새 Teachable Machine 모델 주소로 바꾸세요. 클래스 이름은 `left`, `right`, `up`, `down`이어야 합니다.

## 실행 방법

웹캠은 `https` 또는 `localhost`에서만 동작하므로 로컬 서버로 실행하세요.

```bash
python -m http.server 8000
```

브라우저에서 http://localhost:8000 접속 → **📷 웹캠 시작** → 카메라 허용 → **▶ 게임 시작**
(운석 피하기는 http://localhost:8000/dodge.html)

## 설정

- **인식 기준**: 클래스 확률이 이 값 이상일 때만 방향을 바꿉니다.
- **속도**: 뱀이 움직이는 간격(ms)입니다. (뱀 게임)
- **카메라**: 카메라가 여러 개면 여기서 고릅니다.

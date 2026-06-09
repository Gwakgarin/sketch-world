# SKETCH WORLD

손 제스처로 그림을 그리고, AI가 수채화·유화·애니 스타일로 변환해주는 웹 앱입니다.

![preview](https://github.com/user-attachments/assets/placeholder)

## 기능

- **손 제스처 드로잉** — 웹캠만으로 그리기/지우기/멈춤 제스처 인식
- **브러시 3종** — 연필, 마커, 수채화 (각기 다른 질감)
- **색상 팔레트** — 12색 프리셋 + 커스텀 컬러피커
- **Undo / Redo** — 획 단위 실행취소 (버튼 또는 Ctrl+Z)
- **AI 스타일 변환** — ControlNet Scribble로 스케치 구조를 유지하며 스타일 적용
  - 수채화 / 유화 / 애니 / 펜스케치
- **결과 저장** — AI 변환 이미지 PNG 다운로드

## 제스처

| 제스처 | 동작 |
|--------|------|
| ✏ 검지만 펴기 | 그리기 |
| ✊ 주먹 | 지우기 |
| ✌ 검지 + 중지 | 멈춤 |

## 실행 방법

### 사전 조건
- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 로컬 실행 중 (포트 8000)
- `dreamshaper_8.safetensors` 체크포인트
- `control_scribble.pth` ControlNet 모델

### ComfyUI 시작

```bash
python main.py --port 8000 --enable-cors-header
```

### 앱 실행

```bash
# 프로젝트 폴더에서
python3 -m http.server 3000
```

브라우저에서 `http://localhost:3000` 접속 후 웹캠 권한 허용.

## 기술 스택

- **MediaPipe Hands** — 손 랜드마크 실시간 추적
- **HTML5 Canvas** — 브러시 렌더링
- **ComfyUI API** — Stable Diffusion + ControlNet 워크플로우
- **DreamShaper 8** — 기본 생성 모델
- **ControlNet Scribble** — 스케치 구조 보존

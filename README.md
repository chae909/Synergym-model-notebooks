# Synergym Model Notebooks

이 저장소는 Synergym 프로젝트의 AI/ML 모델 개발 및 훈련을 위한 Jupyter 노트북들을 포함합니다.

## 📁 프로젝트 구조

```
Synergym-model-notebooks/
├── emotion/                    # 감정 분석 모델
│   ├── KcELECTRA.ipynb        # KcELECTRA 모델 훈련
│   └── Upload_Emotion.ipynb    # 훈련된 모델 HuggingFace 업로드
├── yolo/                      # 자세 추정 모델
│   ├── Yolo_Train.ipynb       # YOLO 포즈 모델 훈련
│   └── coco8-pose.yaml        # YOLO 훈련 설정 파일
└── README.md
```

## 🚀 주요 모델

### 1. 감정 분석 모델 (Emotion Analysis)

#### `emotion/KcELECTRA.ipynb`
- **목적**: 한국어 텍스트의 감정을 분류하는 모델 훈련
- **모델**: KcELECTRA (Korean ELECTRA)
- **주요 기능**:
  - KcELECTRA 기반 감정 분류 모델 파인튜닝
  - 훈련/검증 데이터 전처리
  - 모델 성능 평가 및 시각화
  - 최적 모델 저장

#### `emotion/Upload_Emotion.ipynb`
- **목적**: 훈련된 감정 분석 모델을 HuggingFace Hub에 업로드
- **주요 기능**:
  - 로컬 모델을 HuggingFace Hub에 업로드
  - 모델 테스트 및 검증
  - 배포 준비

### 2. 자세 추정 모델 (Pose Estimation)

#### `yolo/Yolo_Train.ipynb`
- **목적**: 운동 자세 추정을 위한 YOLO 모델 훈련
- **모델**: YOLOv11x-pose
- **주요 기능**:
  - YOLO 포즈 추정 모델 훈련
  - 훈련 과정 모니터링
  - 성능 분석 및 결과 시각화
  - 모델 저장 및 내보내기

#### `yolo/coco8-pose.yaml`
- **목적**: YOLO 모델 훈련을 위한 설정 파일
- **포함 내용**:
  - 데이터셋 경로 설정
  - 클래스 정의
  - 키포인트 정의

## 🛠️ 사용 환경

### 필요 라이브러리

#### 감정 분석 모델
```bash
pip install transformers datasets accelerate evaluate
pip install torch torchvision
pip install scikit-learn matplotlib
```

#### 자세 추정 모델
```bash
pip install ultralytics
pip install matplotlib pandas
```

### 실행 환경
- **권장**: Google Colab (GPU 사용)
- **로컬 환경**: Python 3.8+ with CUDA (선택사항)

## 📊 모델 성능

### 감정 분석 모델
- **모델명**: `iuj92/synergym_emotion`
- **베이스 모델**: KcELECTRA
- **지원 감정**: 다중 감정 분류
- **HuggingFace Hub**: https://huggingface.co/iuj92/synergym_emotion

### 자세 추정 모델
- **모델**: YOLOv11x-pose
- **용도**: 운동 자세 키포인트 검출
- **지원 포맷**: ONNX, TensorRT (변환 가능)

## 🔧 사용 방법

### 1. 감정 분석 모델 훈련
```bash
# KcELECTRA.ipynb 노트북 실행
# 1. 데이터 준비 (emotion_train.jsonl, emotion_val.jsonl)
# 2. 모델 훈련 실행
# 3. 최적 모델 저장

# 모델 업로드
# Upload_Emotion.ipynb 노트북 실행
```

### 2. 자세 추정 모델 훈련
```bash
# Yolo_Train.ipynb 노트북 실행
# 1. 데이터셋 준비
# 2. 설정 파일 수정 (coco8-pose.yaml)
# 3. 모델 훈련 실행
```

## 📝 주의사항

1. **Google Colab 사용 시**:
   - Google Drive 마운트 필요
   - GPU 런타임 선택 권장
   - 세션 시간 제한 고려

2. **데이터 준비**:
   - 감정 분석: JSONL 형식의 라벨링된 텍스트 데이터
   - 자세 추정: YOLO 형식의 키포인트 어노테이션 데이터

3. **모델 저장**:
   - 정기적인 체크포인트 저장
   - 최적 모델 백업

## 🤝 기여 방법

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.

---

**Synergym Team**  
AI/ML 모델 개발 및 연구

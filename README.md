# 💬 한국어 영화 리뷰 감성 분석 (Sentiment Analysis with LSTM)

## 🎯 프로젝트 개요

이 프로젝트는 **$\text{Naver}$ 영화 리뷰 ($\text{NSMC}$) 데이터셋**을 활용하여 한국어 문장의 감성(긍정/부정)을 자동으로 분류하는 **$\text{Deep Learning}$ 분류기**를 구축했습니다. **$\text{Konlpy}$ 형태소 분석기**를 통해 한국어 텍스트를 전처리하고, **임베딩(Embedding)**과 **$\text{LSTM}$ (Long Short-Term Memory)** 아키텍처를 사용하여 문맥 정보를 효과적으로 학습했습니다.

## 💡 주요 기술 및 모델 구조

| 분야 | 기술/라이브러리 | 역할 |
| :--- | :--- | :--- |
| **데이터셋** | $\text{Naver}$ Sentiment Movie Corpus ($\text{NSMC}$) | 15만 건의 영화 리뷰 및 긍정/부정(1/0) 레이블 |
| **전처리** | $\text{Konlpy}$ ($\text{Okt}$ 형태소 분석기) | 한국어 형태소 분석 및 불용어(Stopwords) 제거 |
| **핵심 모델** | **$\text{Embedding}$ $\rightarrow$ $\text{LSTM}$ $\rightarrow$ $\text{Dense}$** | 텍스트를 100차원 벡터로 변환하고 순서 정보를 학습 |
| **결정 요인** | **정수 인코딩, 패딩 ($\text{Max\_len}=30$)** | 모든 입력 시퀀스를 딥러닝 모델에 적합하도록 정규화 |

## 🧠 모델 최종 성능 및 결과

### 1. 테스트 결과 (Test Set Evaluation)

학습된 모델을 약 5만 건의 테스트 데이터에 적용한 결과입니다.


| **테스트 데이터 개수** | 49,430개 |
| **최종 정확도 ($\text{Accuracy}$)** | **0.8284 (82.84%)** |
| **손실 ($\text{Loss}$)** | 0.8508 |

> 모델은 테스트 셋에서 82% 이상의 정확도로 영화 리뷰의 감성을 예측하는 데 성공했습니다.

### 2. 학습 지표 시각화

모델이 학습되는 10번의 에포크($\text{Epoch}$) 동안 **훈련 정확도**가 **0.9804**까지 상승했음을 확인할 수 있습니다.

* **Epoch 10 결과:** Training Accuracy: 0.9804, Validation Accuracy: 0.8334, Validation Loss: 0.8284
    * **과적합(Overfitting) 발생:** 훈련 정확도는 높지만, 검증 정확도와 손실($\text{Loss}$)이 2 Epoch 이후부터 발산하는 경향을 보여, **모델이 훈련 데이터에 과적합**되었음을 알 수 있습니다. 이는 향후 Dropout 또는 Early Stopping을 적용하여 개선할 수 있는 지점입니다.

### 3. 사용자 문장 예측 테스트 (Real-world Prediction)

| 문장 | 예측 감성 | 예측 확률 |
| :--- | :--- | :--- |
| 이 영화 정말 최고예요 다시 보고 싶어요 | 긍정 ($\text{Positive}$) | 1.00 |
| 시간 낭비했어요 스토리가 너무 엉성해요 | 부정 ($\text{Negative}$) | 1.00 |
| 배우들 연기는 좋았지만 결말이 아쉽네요 | 부정 ($\text{Negative}$) | 0.83 |

---

## 💻 프로젝트 파일 및 실행 방법

1.  **노트북 파일:** [감성 분석 Colab 노트북 바로가기](./NLP 문장 임베딩 기반 감성 분석.ipynb)
2.  **환경:** $\text{Google Colaboratory}$ ($\text{GPU}$ 런타임 권장)
3.  **실행:** 노트북 파일을 열고 **`런타임` $\rightarrow$ `모두 실행`**을 통해 전체 과정을 재현할 수 있습니다.

---

## ➡️ 다음 작업

이 $\text{README.md}$를 $\text{GitHub}$에 적용하기 위해 필요한 최종 작업은 다음과 같습니다.

1.  **$\text{Colab}$ 노트북 다운로드:** $\text{Colab}$ 파일을 `.ipynb` 형식으로 다운로드합니다.
2.  **시각화 이미지 저장:** 마지막 단계에서 출력된 **정확도/손실 그래프 이미지**를 `.png` 파일로 저장합니다.
3.  **GitHub 업로드:** 두 파일을 $\text{GitHub}$ 프로젝트 폴더에 업로드합니다.
4.  **$\text{README.md}$ 적용:** $\text{GitHub}$ 웹사이트에서 이 초안 내용으로 $\text{README}$를 교체합니다.


# 💬 한국어 영화 리뷰 감성 분석 (Sentiment Analysis with LSTM)

## 🎯 프로젝트 개요

이 프로젝트는 **$\text{Naver}$ 영화 리뷰 ($\text{NSMC}$) 데이터셋**을 활용하여 한국어 문장의 감성(긍정/부정)을 자동으로 분류하는 딥러닝 모델을 구축하는 실습입니다. **임베딩(Embedding)**을 통해 텍스트를 벡터화하고, **$\text{LSTM}$ (Long Short-Term Memory)** 구조를 사용하여 문장의 **문맥과 순서 정보**를 학습했습니다.

## 💡 주요 기술 및 모델 구조

| 분야 | 기술/라이브러리 | 역할 |
| :--- | :--- | :--- |
| **데이터셋** | $\text{Naver}$ Sentiment Movie Corpus ($\text{NSMC}$) | 20만 건 이상의 영화 리뷰 및 긍정/부정(1/0) 레이블 |
| **전처리** | $\text{Konlpy}$ ($\text{Okt}$ 형태소 분석기) | 한국어 문장 토큰화 및 불용어(Stopwords) 제거 |
| **모델 구조** | **$\text{Embedding}$ $\rightarrow$ $\text{LSTM}$ $\rightarrow$ $\text{Dense}$** | 텍스트를 벡터로 변환하여 순차적으로 학습하고 최종 분류 |
| **핵심 이론** | **임베딩**, $\text{Recurrent Neural Network (RNN)}$ | 텍스트를 숫자 벡터로 변환하여 단어 간의 관계를 파악 |

## 🧠 모델 성능 및 학습 과정

**최종 정확도:** 87.xx% 이상 (학습 결과에 따라 변동 가능)

### 📈 학습 지표 시각화

모델이 학습되는 과정에서 **손실(Loss)**과 **정확도(Accuracy)**가 안정적으로 수렴했음을 보여주는 그래프입니다. (이 이미지를 $\text{GitHub}$에 업로드하고 아래 경로를 수정하여 삽입하세요.)

![Model Training History (Accuracy and Loss)](./YOLOv9_Object_Detection/results/sentiment_history.png)

### 💬 실제 예측 테스트 결과

새로운 문장을 입력했을 때 모델이 정확하게 감성을 분류하는지 확인한 결과입니다.

| 문장 | 예측 감성 | 예측 확률 |
| :--- | :--- | :--- |
| 이 영화 정말 최고예요. 다시 보고 싶어요! | 긍정 ($\text{Positive}$) | 0.9X |
| 시간 낭비했어요. 스토리가 너무 엉성해요. | 부정 ($\text{Negative}$) | 0.XX |
| 배우들 연기는 좋았지만, 결말이 아쉽네요. | 부정 ($\text{Negative}$) | 0.XX |

## 💻 실습 파일 및 실행 방법

1.  **노트북 파일:** [감성 분석 $\text{Colab}$ 노트북 바로가기](./sentiment_analysis_notebook.ipynb) (실제 파일 이름으로 수정)
2.  **환경:** $\text{Google Colaboratory}$ ($\text{GPU}$ 런타임 권장)
3.  **실행:** 노트북 파일의 셀을 순서대로 실행하며 **데이터 전처리, 임베딩, $\text{LSTM}$ 학습** 과정을 확인할 수 있습니다.

---

### 📌 다음 작업 (GitHub 웹사이트에서)

1.  **$\text{Colab}$ 노트북 다운로드:** $\text{Colab}$에서 이 노트북 파일을 **`.ipynb`**로 다운로드합니다.
2.  **학습 결과 이미지 저장:** 마지막 단계에서 출력된 **학습 과정 시각화 그래프**를 이미지 파일(`sentiment_history.png` 등)로 저장합니다.
3.  **GitHub 업로드:** 1단계처럼 `YOLOv9_Object_Detection/results` 폴더 안에 **결과 이미지**를 업로드하고, 루트에 **`.ipynb` 파일**을 업로드합니다.
4.  **$\text{README.md}$ 수정:** $\text{GitHub}$ 웹사이트에서 기존의 $\text{README}$ 내용을 이 초안으로 **전부 교체**하고 저장합니다.

# 🧬 머신러닝 프로젝트: 바이러스 vs 인간 단백질 분류 및 클러스터링

> AlphaFold의 노벨화학상 수상에서 영감을 받아, 단백질 구조 데이터를 활용하여 바이러스 단백질과 인간 단백질을 분류하고 클러스터링하는 머신러닝 기반 생물정보학 프로젝트

---

## 📌 프로젝트 개요

* **주제**: 단백질 구조 정보를 바탕으로 바이러스와 인간의 단백질을 머신러닝으로 구분하고, 유사도 기반 군집 분석 수행
* **배경 동기**: AlphaFold의 단백질 구조 예측 기술의 중요성이 부각되며, 생물학과 AI의 융합 가능성 제시

---

## 🧪 데이터 설명

### 📚 데이터 출처

* **PDB (Protein Data Bank)**: 전 세계 생물학자들이 사용하는 단백질 구조 데이터 저장소

### 📦 데이터 구성

* 바이러스 단백질 약 1,000개
* 인간 단백질 약 1,000개
* 각 파일은 하나의 단백질 구조 정보 포함 → 벡터화 과정을 통해 머신러닝 입력 형태로 가공

---

## 🎯 문제 정의

### 🔹 분류 (Classification)

* 목적: 주어진 단백질이 바이러스 유래인지, 인간 유래인지를 분류
* 방법: 지도학습 기반 모델(Logistic Regression, SVM, Decision Tree 등)

### 🔹 클러스터링 (Clustering)

* 목적: 사전 라벨 없이 유사 구조 단백질끼리 군집화 → 자연스러운 군집 형성 여부 확인
* 방법: PCA, LDA 차원 축소 + KMeans / DBSCAN 등 적용

---

## 🧱 분석 방법론

### 1. 데이터 전처리

* 결측값 처리: 평균값 대체
* 이상치 제거: IQR 기반 필터링
* 스케일링: 표준 정규화 적용

### 2. 시각화 및 탐색

* 변수 분포 확인
* 상관행렬 히트맵 시각화

### 3. 모델링 (분류)

* 분할: Train/Test Set 분할
* 모델: 로지스틱 회귀, SVM, 의사결정나무, 랜덤포레스트 등
* 튜닝: Grid Search 기반 하이퍼파라미터 최적화
* 앙상블: Voting / StackingClassifier 적용
* 성능평가: F1 Score, Accuracy 시각화

### 4. 특징 중요도 분석

* Feature Importance (Random Forest, Permutation Importance)
* Logistic Regression 계수 기반 해석

### 5. 클러스터링 분석

* 주요 특징 선택: Gradient Boosting 기반
* 차원 축소: PCA, LDA
* KMeans 군집화 및 silhouette score 계산
* DBSCAN 실험 (결과 비의미적)

---

## 🧾 주요 결과 요약

### ✅ 분류 성능

* SVM (C=10, RBF Kernel) 모델에서 **F1 Score: 0.89** 기록
* 결정적인 특징: 아미노산 \*\*Threonine(T)\*\*의 존재 및 분포
* Threonine은 바이러스 vs 인간 단백질 구분에 있어 생화학적으로 중요한 역할 수행

### ✅ 클러스터링 결과

* PCA 변환 후 KMeans 군집 결과 유사함
* Silhouette score는 3개 군집에서 가장 높았으나, 2개 군집이 의미상 타당

---

## 💡 결론 및 의의

* Threonine을 비롯한 특정 아미노산의 특성(분극성, 분포 등)은 유의미한 분류 기준이 될 수 있음
* 구조 기반 특징과 생화학적 전문지식을 융합한 머신러닝 접근법은 단백질 분류 문제에 강력한 도구로 활용 가능함

---

## 파일 내용

1. 머신러닝_MACHINE_LEARNING_PROJECT_-_PDF_(Oh_Dong_Geun_w_Lee_Soo_Haeng).pdf
   > 탐구 과정이 정리되어있는 보고서

---

> ⓒ 2025 | Oh DongGeun & Lee SooHaeng | 바이러스 vs 인간 단백질 분류 머신러닝 프로젝트


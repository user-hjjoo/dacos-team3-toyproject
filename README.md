# Amazon Product Rating Classification & LLM-based Interpretation
## 아마존 상품 평점 등급 분류 및 LLM 기반 결과 해석

## 프로젝트 목표
- 수치 피처(가격, 할인율, 리뷰 수)로 아마존 상품의 평점 등급(Low/Mid/High)을 예측하는 분류 모델 구축
- ML 모델이 찾아낸 피처 중요도 패턴을 리뷰 텍스트와 함께 LLM에 전달해 "왜 그런 패턴이 나타나는가"를 자연어로 해석
- 인사이트 가설 3가지 검증

## 데이터 설명
- 출처: Kaggle — Amazon Sales Dataset
- 데이터 크기: 1,465행 × 16열

### 입력 피처 (X)
- discounted_price
- actual_price
- discount_percentage
- rating_count
- category

### 타깃 (y)
- rating
  - Low: ~3.9
  - Mid: 4.0~4.3
  - High: 4.4~

  ※ 평점 구간은 EDA 기반 분포 분석 후 설정

### LLM 입력 데이터
- review_title
- review_content

## 사용 기술
- Language: Python
- Data Analysis: pandas, numpy
- Visualization: matplotlib, seaborn
- Machine Learning: scikit-learn (모델 클래스 추가할 예정)
- LLM: Gemini API (google-generativeai)
- Development Environment: VS Code
- Version Control: Git / GitHub

## 프로젝트 구조
```
dacos-team3-toyproject/

├── README.md
│
├── data/
│   ├── raw/
│   │   └── amazon.csv
│   │
│   └── processed/
│       ├── processed_data.csv
│       ├── X_train.csv
│       ├── X_test.csv
│       ├── y_train.csv
│       └── y_test.csv
│
├── notebooks/
│   ├── 01_edaNprocessing.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_llm_analysis.ipynb
│
├── docs/
│   ├── project_plan.md
│   ├── troubleshooting.md
│   └── retrospective.md
│
└── results/
    ├── figures/
    │   ├── rating_distribution.png
    │   ├── correlation_heatmap.png
    │   ├── feature_importance.png
    │   └── confusion_matrix.png
    │
    └── metrics/
        └── model_scores.csv
```

## 프로젝트 파이프라인

EDA & 전처리 → 베이스라인 모델 → 앙상블 모델 → GridSearchCV 튜닝 → LLM 해석 → 대시보드

## 주요 결과

## 회고
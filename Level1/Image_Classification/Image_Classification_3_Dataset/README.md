# 3. Dataset

**Vanilla Data를 원하는 형태의 Dataset으로 만드는 과정 필요**

- **Pre-processing**
  - Bounding Box
  - resize
    - 손실보다 빠른 학습의 효율이 높음
- **Generalization**
  - Bias & Variance
    - Underfitting(High Bias)
    - Overfitting(High Variance)
  - Train & Validation
    - 훈련 셋 중 일정 부분을 테스트 셋으로 분리
  - Data Augmentation
    - 주어진 데이터가 가질 수 있는 Case, State의 다양성
    - `torchvision.transforms`
      - random crop, flip 등
      - 유사 library로 Albumentations 등이 있음





**"무조건 좋은 결과를 가져다주는 방법은 없음"**

실험으로 증명할 것

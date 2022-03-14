# 7. Training & Inference 1

- **Loss**
  - = Cost, Error
  - Output과 Target의 차이
  - `nn.Module` family
  - `.backward()` 함수가 실행되면 모델 파라미터의 grad 값이 업데이트
    - `required_grad=false` 제외
  - Focal Loss
    - Class Imbalance 문제가 있는 경우, 맞춘 확률이 높은 Class는 조금의 loss를
      맞춘 확률이 낮은 Class는 Loss를 높게 부여
  - Label Smoothing Loss
    - Class target label을 Onehot 표현으로 사용하기 보다는 조금 Soft하게 표현해
      일반화 성능을 높임
      - 예: [0, 1, 0, 0, 0] → [0.025, 0.9, 0.025, 0.025]



- **Optimizer**
  - 어떤 방향으로 얼마나 움직이게 만들 지 결정
  - LR scheduler
    - Learning rate를 동적으로 움직이게 하는 장치
    - `StepLR`, `CosineAnnealingLR`, `ReduceLROnPlateau`





- **Metric**
  - 모델 평가의 지표
  - 학습에 직접 사용되는 것은 아니더라도, 학습된 모델을 객관적으로 평가할 수 있는 지표가 필요
  - Class별로 밸런스가 적절히 분포되는 지 확인 필요

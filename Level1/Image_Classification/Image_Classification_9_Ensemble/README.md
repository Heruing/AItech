# 9. Ensemble

**싱글 모델보다 나은 성능을 위해 서로 다른 여러 학습 모델을 사용하는 것**

- Model Averaging
  - Voting
    - hard
    - soft
- Cross Validation(CV score)
  - Stratified K-Fold Cross Validation
- Test Time Augmentation
  - 테스트 이미지를 Augmentation 후 모델 추론, 출력된 여러가지 결과를 앙상블





**앙상블 효과는 확실히 있지만, 그 만금 학습과 추론에 시간이 배로 소요됨**





**Hyperparameter**

- 시스템의 매커니즘에 영향을 주는 주요 파라미터
- 변경할 때 마다 학습 필요



여러 학습이 진행된 후 목적에 따라 사용

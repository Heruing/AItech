# Hyperparameter Tuning

- **Hyperparameter**
  - learning rate, batch size 등 사람이 지정하는 모델 외적 요소



- 딥 러닝 결과물에 영향을 주는 요소
  - 모델
    - 중요도는 높으나 정형화(표준화)된 모델이 있는 경우가 많아 영향이 적음
  - 데이터
    - 많으면 많을 수록 좋음
    - 가장 큰 영향을 주는 요소
  - Hyperparameter Tuning
    - 데이터 양의 급증으로 중요성은 감소
    - 미세 조정이 필요할 때 필요



- **Hyperparameter Tuning**
  - Grid search
  - Random search
  - 최근 트렌드는 베이지안 기반 기법



- **Ray**
  - multi-node multi processing 지원 모듈
  - ML/DL의 병렬 처리를 위해 개발된 모듈
  - 기본적으로 현재의 분산병렬 ML/DL 모듈의 표준
    - Hyperparameter Search를 위한 다양한 모듈 제공
  - 학습 스케줄링 알고리즘 지정
    - 가망이 없는 데이터는 버리고 넘어갈 수 있음

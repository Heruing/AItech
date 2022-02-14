# Multi-GPU 학습

엄청난 양의 데이터를 다루기 위해 Multi-GPU의 영역으로 넘어옴

- **Multi-GPU를 사용하는 방법**
  - **모델 병렬화**
    - 이전부터 써오던 방법으로 병목, 파이프라인의 어려움으로 인해 고난이도
  - **데이터 병렬화**
    - 데이터를 나눠 GPU에 할당 후 결과의 평균을 구하는 방법
    - minibatch 수식과 유사한 방식으로 여러 GPU에서 수행
    - 여러 GPU가 연산을 하고, loss값을 하나의 GPU로 모아 gradient를 Backward로 전달
      → Global Interpreter Lock으로 인해 데이터가 분배됐다가 모였다 반복
      → GPU사용 불균형 문제가 발생 → 병목 방지를 위해 Batch사이즈 감소



- **DistributedDataParallel**
  - sampler를 사용하며 `shuffle = False`, `pin_memory = True`로 설정
  - mapping
  - `main_worker: gpu 수  `, `batch_size`와 `num_worker`를 GPU 수로 나눔
  - 멀티프로세싱 통신 규약 정의

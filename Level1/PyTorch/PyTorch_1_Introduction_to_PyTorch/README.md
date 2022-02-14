## Introduction to PyTorch

#### PyTorch

딥러닝을 위한 '프레임워크'

- Dynamic Computation Graph(DCG)
  - PyTorch
  - 연산의 과정을 그래프로 표현
  - Define by Run
    - 실행하면서 그래프를 생성하는 방식

- Define and Run
  - Tensorflow
  - 그래프를 먼저 정의한 후 실행시점에 데이터 feed

- **Why PyTorch?**
  - Define by Run의 장점

    - 즉시 확인 가능 →Pythonic code
    - GPU support, API, community
    - 사용하기 편한 것
    - Tensorflow는 Production, Cloud, Multi-GPU에서 강점

  - Numpy 구조를 가지는 Tensor 객체로 array표현
  - 자동미분을 지원하여 DL연산을 지원
  - 다양한 형태의 DL을 지원하는 함수와 모델을 지원

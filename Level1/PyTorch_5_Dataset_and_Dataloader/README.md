# Dataset & Dataloader

**모델에 데이터를 먹이는 법**(feeding)

- 전처리 → 데이터set → 데이터 loader → model



**Dataset 클래스**

- 데이터 입력 형태를 정의하는 클래스
- 데이터를 입력하는 방식의 표준화
- Image, Text, Audio 등에 따른 다른 입력 정의
- 일반적으로 dict 타입으로 반환하는 경우가 많음
- 유의점
  - 데이터 형태에 따라 각 함수를 다르게 정의
  - 학습에 필요한 시점에 변환해도 상관 없음
    - transform
  - 표준화된 처리방법 제공 필요
    - 후속 연구자와 협업
  - Hugging Face 등 표준화된 라이브러리 사용



**DataLoader 클래스**

- Data의 Batch를 생성하는 클래스
- 학습직전 데이터의 변환을 책임
- Tensor로 변환 + Batch 처리가 주업무
- 병렬적인 데이터 전처리 코드의 고민 필요
- sampler: 데이터를 어떻게 뽑을 지 인덱스를 컨트롤하는 방법

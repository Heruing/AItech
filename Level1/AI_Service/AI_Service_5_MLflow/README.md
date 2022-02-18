## 5. MLflow

#### 1. MLflow 개념 잡기

- MLflow가 없던 시절
  - 각자의 코드를 Jupyter Notebook에서 작성하고 ML모델 학습 시 Parameter와 Metric 따로 기록
  - Memory Exceed 오류 발생
  - Weight File을 따로 저장해 다른 동료들에게 공유
  - Versioning이 어려움

1. MLflow란?
   - 머신러닝 실험, 배포를 쉽게 관리할 수 있는 오픈소스 ML
   - 해결하고자 했던 부분
     - 실험 추적이 어려움
     - 코드 재현이 어려움
     - 모델 패키징과 배포가 어려움
     - 중앙 저장소가 없음
   - 관련 오픈소스 중 제일 빠르게 성장 중
   - CLI, GUI 지원
   - 핵심기능
     1. Experiment Management & Tracking
        - 실험을 관리하고 내용을 기록
        - 실험을 정의하고 실행 가능
     2. Model Registry
        - 머신러닝 모델을 Model Registry에 등록 가능
        - 저장될 때마다 버전이 자동으로 업데이트
        - git, docker와 유사
     3. Model Serving
        - REST API로 Serving 가능
   - 구성
     1. MLflow Tracking
        - 머신러닝 코드 실행, 로깅을 위한 API, UI
        -  결과를 Local, Server에 기록해 비교가능하며 협업을 도움
     2. MLflow Project
        - 프로젝트 코드를 패키징하기 위한 표준
     3. MLflow  Model
        - 모델은 모델 파일과 코드로 저장
        - 다양한 플랫폼에 배포할 수 있는 도구 제공
     4. MLflow  Registry
        - MLflow Model의 전체 Lifecycle에서 사용할 수 있는 중앙 모델 저장소
2. Mlflow 실습하며 알아보기
3. MLflow 아키텍처



#### 2. MLflow 서버로 배포하기

1. Tracking Server와 외부 스토리지 사용하기
2. MLflow 실제 활용사례

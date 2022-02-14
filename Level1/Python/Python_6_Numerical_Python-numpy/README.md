## Numerical Python - numpy

- **Numpy**
  - 다양한 matrix를 표현하기 위한 python 패키지
  - 파이썬의 고성능 과학 계산용 패키지
    - 증권, 이학, 공학 등 다양한 분야에서 활용
  - Matrix와 Vector와 같은 Array연산의 사실상의 표준



- **특징**

  - 일반 List에 비해 빠르고 메모리 효율적

  - 반복문 없이 데이터 배열에 대한 처리를 지원

  - 선형대수 관련 기능 제공

  - C, C++등 언어와 통합 가능

    

- Array creation

  - `np.array` 함수를 활용해 `ndarray` 객체 생성

  - C의 Array를 사용하여 배열 생성

  - List와의 차이

    - dynamic typing not supported

    - 하나의 데이터 type만 배열에 넣을 수 있음



- Array Shape
  - (*l*, *m*, *x*)
    - *x*: 1차원, *m*: 2차원, *l*: 3차원
    - dimension이 늘어날 때마다 한 칸씩 밀려남
- Array reshape
  - `reshape`: Array 의 element 개수를 유지한 상태로 shape 크기를 변경
  - `flatten`: 다차원 array를 1차원 array로 변환



- Indexing
  - [n, m]표기법을 사용 가능
  - matrix 기준 앞은 row, 뒤는 column



- slicing
  - `[a:b, c:d]`
    - row의 a~b-1, column의 c~d-1
    - `[:2, :]` : row는 0, 1 column은 전체
  - `[n]`
    - 2차원 행렬에 [n] index를 호출하면 각 row의 모든 n번째 항이 배열로 추출
- `np.arrange(start, end, step)`
  - float 단위로 step 가능
  - list로 반환
- `ones`, `zeros`, `empty`
  - `ones`: 1로 가득찬 ndarray 생성
  - `zeros`: 1로 가득찬 ndarray 생성
  - `empty`: shape만 주어지고 비어있는 ndarray생성
    - memory initialization이 안 됨
  - `np.one_like(matrix)`, `np.zeros_like(matrix)`
    - matrix와 같은 shape의 0 또는 1로 가득찬 matrix 반환
- `np.identity(n)`
  - 대각행렬이 1이고 크기가 n인 단위행렬 생성
- `np.eye(N, M, k)`
  - 대각선이 1인 행렬로 k번째부터 대각선에 1
  - N:row, M:column
- `diag`
  - 대각 행렬의 값을 추출
- random sampling
  - `np.random.uniform`: 균등분포
  - `np.random.normal`: 정규분포



- `axis`
  - operation function을 실행할 때 기준이 되는 dimension 축
  - shape index(?)
- `mean`, `std`등 다양한 수학 연산자 제공



- `concatenate`
  - numpy array를 합치는 함수
  - `vstack`
    - vertical stack
  - `hstack`
    - horizontal stack
  - `concatenate`
    - 지정한 axis 를 축으로 합침
- `newaxis`
  - 새로운 축을 추가할 때 사용



- Element-wise operations
  - `+, -, /, *`
  - 같은 위치에 있는 값들 끼리 연산
- Dot product
  - matrix 기본 연산
  - `matix_a.dot(matrix_b)`
- broadcasting
  - shape이 다른 배열 간 연산을 지원
  - 자동적으로 배열이 확장되어 연산되어 매우 주의가 필요



- Numpy Operations
  - 일반적으로 속도는 for loop < list comprehension < numpy
  - Numpy는 C로 구현되어 있어 성능이 확보되나 dynamic typing을 포기
  - 대용량 계산에서 흔히 사용
  - 할당에서는 연산 속도의 이점이 없음





**comparisons**

- `all(condition)`
  - 모두 true일 때 true(AND)
- `any(condition)`
  - 하나라도 true일 때 true(OR)

- 배열의 크기가 동일할 때 element간 비교의 결과를 Boolean type으로 반환
- `where()`
  - `(condition, TRUE, FALSE)` : true, false일 때 각각 출력할 값
  - `(condition)` : true인 값의 index
- `isnan(n)`
  - 메모리 상의 특정 수 찾기
- `isfinite(n)`
  - 발산하는 수 찾기
- `argmax`, `argmin`
  - array내 최대값 또는 최소값의 index
  - axis기반
- `argsort()`
  - 작은 값 부터 index



**boolean & fancy index**

- `array[condition]`
  - array에서 condition에 대하여 true인 값만 반환
- `array condition`
  - true, false를 판별하여 반환
- fancy index
  - `arrayA[arrayB]`
  - numpy는 array를 index value로 사용해서 값 추출



**numpy data i/o**

- `loadtxt(path)`
- `astype`
  - type 변환
- `savetxt('name', array, fmt(foramt),delimiter)`

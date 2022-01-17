## 벡터가 뭐에요?

- **Vector**

  - 숫자를 원소로 가지는 리스트 또는 배열
  - 공간에서 **한 점**을 나타냄
  - 원점으로부터 상대적 위치를 표현

- **Vector 연산**

  - 숫자를 곱해주면 길이만 변화

  - 보통 같은 모양이 아닐 경우 덧셈 뺄셈이 불가능

  - 같은 모양을 가지면 **성분곱**을 계산할 수 있다

  - 두 벡터의 덧셈은 다른 벡터로부터 상대적 위치이동을 표현

  - 뺄셈은 방향을 뒤집은 덧셈과 같음

  - **벡터의 노름(norm)**

    - 원점에서부터의 거리

    - L1-노름은 변화량의 절대값을 모두 더함

      ```python
      def l1_norm(x):
          x_norm = np.abs(x)
          x_norm = np.sum(x_norm)
          return x_norm
      ```

      

    - L2-노름은 피타고라스 정리를 이용해 유클리드 거리를 계산

      ```python
      def l2_norm(x):
          x_norm = x*x
          x_norm = np.sum(x_norm)
          x_norm = np.sqrt(x_norm)
          return x_norm    
      ```

    - 노름마다 기하학적 성질이 달라짐
      

  - 두 벡터 사이의 거리

    - 벡터의 뺄셈을 이용

  - 두 벡터 사이의 각도

    - L2-노름에서만 가능

    - 제2 코사인 법칙에 의해서 각도를 계산

    - ```python
      def angle(x, y):
          v = np.inner(x, y) / (l2_norm(x) * l2_norm(y))
          theta = np.arccos(v)
          return theta
      ```

  - 내적의 해석

    - 정사영된 벡터의 길이와 관련
    - 두 벡터의 유사도를 측정하는 데 사용

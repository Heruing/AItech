## Python과 Matplotlib

#### 1. Matplotlib

- python에서 사용 가능한 시각화 라이브러리로 `numpy`와 `scipy`를 베이스로 함
  - 다양한 라이브러리와 호환성이 좋음(`Scikit-Learn`, `PyTorch`, `Tensorflow`, `Pasdas` ...)
- 다양한 시각화 방법론 제공
  - 막대그래프
  - 선그래프
  - 산점도
  - ETC
- `Seaborn`, `Plotly`, `Bokeh`, `Altair`등 라이브러리가 존재하나 `Matplotlib`가 범용성이 넓음



#### 2. 기본 Plot

1. Figure와 Axes

   - `plt.show()`

   - ``jupyter notebook` 등의 환경에서는 필요없지만, 외부 환경에서는 필요

   - 서브플롯을 너무 많이 추가하면 리소스를 많이 잡아먹기 때문에 100개 정도 까지만

   - `.figure(figsize=(n, m))`

     - n:m사이즈(인치) 

   - 그래프를 2개 이상 그랄 수 있음

     ```python
     ax = fig.add_subplot(121)
     # 1 x 2로 쪼개고, 1번 자리에 subplot을 추가한다
     ax = fig.add_subplot(122)
     # ax = fig.add_subplot(1, 2, 2)로 사용가능
     
     ax = fig.add_subplot(nmk)
     # n x m 으로 쪼개고 k번째 (nmk) → (n, m, k) 하나의 행 부터 채움
     ```

     - 일반적인 python문법과 달리 1부터 index

2. plt로 그래프 그리기

   - `plt.plot()` 마지막 선언된`subplot`에 삽입
     - not pythonic

3. 서브플록 객체 ax에 그리기

   - `ax`객체에 직접 그리기

     ```python
     fig = plt.figure()
     
     x1 = [1, 2, 3]
     x2 = [3, 2, 1]
     
     ax1 = fig.add_subplot(211) 
     ax2 = fig.add_subplot(212) 
     
     ax1.plot(x1)		# plt.plot(x1) 사용시 subplot2에만 두 개 직선
     ax2.plot(x2)
     ```



#### 3. Plot의 요소들 알아보기

1. 한 서브 플롯에서 여러 개 그리기

   - ax에는 동시에 다양한 그래프 생성 가능
   - 기본 설정은 파랑, 주황, 초록, 빨강.. 순서
     - 다른 종류의 그래프(선과 막대 등)를 그리면 색은 다시 시작(파랑, 파랑)
     - 다른 종류의 그래프를 사용 시 색을 명시하는 것이 좋음

2. 색상 지정하기

   - `plot=(array, color="c")`
     - 한 글자로 정하는 색상, color name, hex code(#000000)로 지정 가능

3. 텍스트 사용하기

   - `label`

     - 시각화에서는 드러나지 않는 labeling

     - 보여주려면 범례(`label()`)을 추가해야 함

       ```python
       ax. legend()
       ```

   - `title`

     - `set_title()`: subplot에 제목 붙이기
     - `suptitle()`: figure에 제목 붙이기
     - `get_title()`: title 추출

   - `ticks`와 `ticklabels`

     - `ticks`: 축에 적히는 수 위치를 지정
     - `ticklabels`: 축에 적히는 텍스트를 수정

   - `text(x=x, y=y, s=string)`

   - `annotate(text, point)`

     - 원하는 지점에 텍스트 추가하기
     - 화살표를 추가할 수 있는 장점

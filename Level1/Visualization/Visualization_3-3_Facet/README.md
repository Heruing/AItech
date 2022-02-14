## Facet

#### 1. Facet

1. Multiple View
   - Facet이란 분할을 의미
   - 화면 상에 View를 분할 및 추가하여 다양한 관점을 전달
     - 같은 데이터 셋에 서로 다른 인코딩을 통해 다른 인사이트를 제공
     - 같은 방법으로 동시에 여러 feature를 보거나 부분 집합을 세세하가 보여줌

#### 2. Matplotlib에서의 구현

1. Figure와 Axes
   - figure는 큰 틀, Ax는 각 플롯이 들어가는 공간
   - figure는 1개, plot은 N개
2. N x M subplots
   - 방법
     - `plt.subplot()`
     - `plt.figure() + fig.add_subplot()`
     - `plt.subplots()`
   - 조정 요소
     - `figuresize`
     - `dpi`
     - `sharex`, `sharey`
     - `squeeze`
     - `aspect`
3. Grid Spec의 활용
   - 그리드 형태의 subplots
   - `fig.add_grid_spec()`
   - `fig.subplot2grid()`
4. 내부에 그리기
   - `ax.inset_axes()`
     - ax 내부에 서브플롯을 추가하는 방법
   - `make_axes_locatable(ax)`
     - 사이드에 추가하기





**실습**

- DPI: 데이터 학습중에는 낮춰뒀다가, 저장할 때 높이는 것을 권장
- `.savefig('filename', dpi=)` 원하는 해상도 png 파일로 저장
- `squeeze`
  - 1 x N 배열인 경우에도 2차원으로 배열을 받을 수 있음
    - 2중 반복문을 사용하기 위해 사용
- `flatten()`
  - 1차원으로 받을 수 있음
- `aspect=n`
  - x축에 대한 y축 길이 비율
- `add_gridspec`
  - 슬라이싱으로 비율 정하기

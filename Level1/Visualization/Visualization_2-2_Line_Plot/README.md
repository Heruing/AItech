## Line Plot 사용하기

#### 1. 기본 Line Plot

1. Line plot이란?
   - 연속적으로 변화하는 값을 순서대로 점으로 나타내 이를 선으로 연결한 그래프
   - 시간/순서에 대한 변화에 적합하여 추세를 살피기 위해 사용
     - 시계열 분석에 특화
2. Line의 요소
   - 5개 이하의 선을 사용하는 것을 추천
   - 구별 요소
     - 색상
       - `color`
     - 마커
       - `marker`, `markersize`
     - 선 종류
       - `linestyle`, `linewidth`
3. Line plot을 위한 전처리
   - 실시간으로 변하는 데이터는 noise로 인해 패턴 및 추세 파악이 어려움
   - noise의 인지적 방해를 줄이기 위해 smoothing 사용



#### 2. 정확한 Line plot

1. 추세에 집중
   - Bar plot과 달리 꼭 축을 0에 둘 필요는 없음
     - 추세를 보기 위한 목적
   - 목적에 따라 너무 구체적인 line plot보다는 생략된 line plot이 더 나을 수 있음
     - grid, annotate등 제거
     - 디테일은 표로 제공
2. 간격
   - 규칙적인 간격이 아니라면 없는 데이터에 대한 오해를 줄 수 있음
     - 마커를 사용하여 처리
3. 보간
   - 데이터가 없는 점과 점 사이를 잇는 방법
   - error나 noise가 포함된 경우 데이터의 이해를 돕는 방법
     - moving average
     - smooth curve with scipy
   - Presentation에는 좋은 방법일 수 있음
     - 없는 데이터에 대한 오해나 작은 차이를 없앨 수 있으므로 일반 분석에서는 지양
4. 이중 축 사용
   - 하나의 plot에 대한 2개의 축
   - 같은 시간 축에 대해 서로 다른 종류의 데이터를 표현 하는 등의 경우
     - `.twinx()`
   - 한 데이터에 대해 다른 단위
     - `.secondary_xaxis()`, `.secondary_yaxis()`사용
   - 특정한 상황이 아니라면 이중 축 보다는 2개의 plot을 권장
5. ETC
   - 범례 대신 line 끝에 정보를 표시
   - min/max 정보는 도움이 될 수 있음
     - annotation
   - uncertainty
     - 살짝 연한 색이나 대비가 강한 색상을 통해 표현 가능
     - area

**실습**

- 기본적으로 (x1, y1) → (x2, y2) 순서로 선을 그음
  - x 값을 정렬하는 것이 좋음
- `marker`
  - `'*'`, `'.'`, `'o'` 등
- `linestyle`
  - solid, dashed, dashdot...
- 이동 평균은 pandas의 `rolling`을 사용
  - 반복문을 사용해도 가능

- y 값만 있어도 plot이 그려지긴 함
  - 되도록 x 값도 채워서 그리기
- secondary axis
  - https://matplotlib.org/stable/gallery/subplots_axes_and_figures/secondary_axis.html

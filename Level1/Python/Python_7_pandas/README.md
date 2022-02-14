## Python Data Anlysis Library - pandas



**Pandas**

- 구조화된 데이터 처리를 지원하는 라이브러리
- 고성능 array 계산 라이브러리 numpy와 통합하여 스프레드 시트 처리기능 제공
- 데이터 처리 및 통계 분석을 위해 사용
- `attribute`, `field`, `feature`, `column` 다양한 이름으로 열 그룹 정의



- `head(n=5)`
  - 처음 n줄 (기본 5줄) 출력
- `columns`
  - column header 이름 지정





**series**

- 하나의 column에 해당하는 데이터 모음
- column vector를 표현하는 object
- data indexing이 문자로도 되어 있음
  - duplicate 가능
- `Series(data = list_data, index = list_name, dtype=np.float32, name="name")`
  - `data` list를 데이터로 지정
  - `index`: 리스트로 index 이름을  지정
  - `dtype`: data type 설정 → `astype(type)`으로도 가능
  - `name`: series 이름 설정
- 기본적으로 index를 기준으로 series 생성



**dataframe**

- Data Table 전체를 포함하는 Object
- dataframe 안의 하나의 값에 접근하기 위해서는 index와 column을 모두 알아야 함
- 기본적으로 series를 모아서 만든 기본 2차원 Data Table
  - 각 series끼리는 data type이 다를 수 있음
- `columns=["a", "b"]`
  - a, b series column을 추출
  - 없는 column을 호출하면 NaN(Not-A-Number) 속성을 갖는 데이터 호출
- `loc`
  - index 이름
  - 지정한 이름의 인덱스가 나올 때 까지 데이터 추출
- `iloc`
  - index number
  - 지정한 값 만큼의 데이터 추출
- `T`
  - transpose
- `values`
  - 값 출력
- `to_csv()`
  - csv 변환
- `dataframe["column"]`
  - 특정 column을 선택
  - `del array["column"]`
    - 메모리 주소 자체를 삭제
  - `drop("column", axis=n)`
    - 해당 column을 axis=n으로 삭제한 dataframe을 반환



**selection**

- `dataframe["column"]`
  - 한 개의 column 선택
- `dataframe[["column1", "column2", "column3"]`
  - 여러 column 선택
- series indexing
  - `series[:n]`
  - `series[[0, 1, 2, 3, ...]]`
  - `series[condition]`
    - boolean index
- `reset_index(drop=, inplace=)`
  - index 0부터 재설정
  - drop을 True로 하면 기존 인덱스 제거한 table 반환
  - inplace를 True로 하면 자기 자신이 변화(drop 등에서 사용 가능)



**dataframe operation**

- **series operation**
  - index를 기준으로 연산 수행
    - 겹치는 index 없을 경우 NaN값으로 반환
- **dataframe operation**
  - column과 index를 모두 고려
  - `fill value=0`
    - 매칭되지 않는 인덱스 값을 0으로 계산
- series + dataframe
  - axis를 기준으로 broadcasting



- `lambda`, `map`, `apply`
  - `map`
    - 지정 범위에 대해 적용
  - `replace`
    - map 함수의 데이터 변환 기능만 담당
  - `apply`
    - map과 달리 serries 전체에 해당 함수 적용



**built-in function**

- `describe`

  - 데이터 요약 정보

- `unique`

  - 유일한 값의 list 반환

- `sum`

  - 기본적인 row 또는 column 연산
  - `sub`, `mean`, `min`, `max`, `count` 등

- `isnull`

  - NaN 값의 index 반환

- `sort_values(["column"], ascending)`

  - column값을 기준으로 sorting
  - column기준, 오름차순, 내림차순

- `corr`, `cov`, `corrwith`

  - 상관계수, 공분산을 구하는 함수

  ★★★ 외우기보다는 필요할 때마다 사용할 수 있도록 기억★★★



**Groupby I**

- SQL groupby 명령어와 같음
  - split → apply → combine 과정을 거쳐 연산
    - split: index가 같은 data끼리 묶기
    - apply: sum 등 적용
    - combine: 적용된 데이터 묶음
- `dataframe.groupby("묶음의 기준 Columns")["적용 받는 Column"].적용연산()`
  - `예시`: `df.groupby("Team")["Points"].sum()`
    - 팀별로 포인트 합산 구하기
  - 한 개 이상의 column을 묶을 수 있음
- **Hierarchical index**
  - Groupby 명령의 결과물도 dataframe
    - 두 개의 column으로 groupby할 경우 두 개의 index 생성
    - `unstack()`, `reset_index()` 등 으로 데이터를 풀어줌
  - `swaplevel()`: index level변경
  - `sort_values()`, `sortlevel(n)` 등으로 정렬 가능
  - index level을 기준으로 기본 연산 수행 가능



**Groupby II**

- Split된 상태의 데이터 추출 가능
  - `groupby("Column")`
    - key, value 형태로 추출 가능
- **apply**
  - `agg`(aggregation)
    - 특정 컬럼에 여러개 function apply 가능
  - `transform`(transformation)
    - agg와 달리 key값 별로 요약된 정보가 아니며 개별 데이터 변환 지원
  - `filter(condition)`
    - 조건에 맞는 데이터 검색



**Case study**

- Data
  시간과 데이터 종류가 정리된 통화량 데이터 예시

  - `dtype`

    - data type을 형태에 맞게 변경
    - `apply(dateutil.parser.parse, dayfirst=True)`

  - `matplotlib`

    ```python
    conda install matplotlib
    ```

    - `plot()`: graph 출력 가능



**Pivot table & Crosstab**

- Pivot Table
  - `.pivot_table(["column"], index), columns, aggfunc, fill_value...`
  - index축은 groupby와 동일
  - column에 labeling 값을 추가하여 value에 numeric type 값을 aggregation하는 형태

- Crosstab
  - 두 column에 교차 빈도, 비율, 덧셈 등을 구할 때 사용
  - Pivot table의 특수형태로 User-Item Rating Matrix 등을 만들 때 사용 가능



**merge & concat**

- **merge**
  - SQL에서 많이 사용하는 merge와 같은 기능으로, 두 개의 데이터를 하나로 합침
  - `.merge(a, b, on='기준 column')`
    - subject_id 기준으로 merge
    - column 이름이 다를 경우 `left_on`과 `right_on`으로 구분
  - join method
    - how로 설정하고 비어있는 값은 NaN이 채워짐
    - inner join: 같은 값을 가진 경우만 합침
    - full join: 전부 합침
    - left join: 왼쪽df에 있는 값만 합침
    - right join: 오른쪽 df에 있는 값만 합침
    - left_index, right_index를 설정하면 index를 기준으로 합침
- **concat**
  - 같은 형태의 데이터를 붙이는 연산작업



**persistence**

- database connection
  - data loading시 db connection 기능을 제공
- XLS persistence
  - Dataframe의 엑셀 추출코드
  - Xls 엔진으로 openpyxls 또는 XlsxWrite 사용
- Pickle persistence
  - 가장 일반적인 python 파일 persistence
  - `to_pickle`, `read_pickle`

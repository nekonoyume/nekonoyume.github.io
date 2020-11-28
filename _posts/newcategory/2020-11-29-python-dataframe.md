---
title: Python - DataFrame 다루기
---

### CSV Read Write

- Read

```python
df = pd.read_csv("dfname.csv", encoding='ansi')
```

> utf-8로 저장할 경우 한글이 깨지는 문제가 간혹 발생한다.
>
> 그럴 경우엔 ansi로 읽고 쓴다.



- Write

```python
df.to_csv("dfname.csv", encoding="ansi")
```



### Indexing

- iloc

``` python
df.iloc[i] #i == 숫자
```

> i번째 행을 불러온다.

- loc

  ```python
  result2.loc[len(result2)] = [nameX, mean]
  ```

  - technique - mask의 사용

```python
mask1 = (result2.average < 1) & (result2.average >= 0.8)
#mask1 = (result2.average == 0)
# df_teenage = titanic.loc[mask1,:]
aaa = result2.loc[mask1, :]

mask1 = (df.average < 0.2) & (df.average >= 0)
mask2 = (df.average == 0 )
aaa = df.loc[mask1, :]
```





- isin

  - 해당 값을 포함한 모든 행들을 골라낼 때

  ``` python
  df[df.Attributes.isin([x])].average.mean()
  ```





###  수정

- null값 제거

  ``` python
  a = a.drop(0, axis = 1)
  ```

  



### 계산

-  mean = resultTemp['Similarity'].mean()
-  



### DataFrame 생성

- 초기값, Columns만 잡아주고 만들기

  ```python
  empty = []
  df = pd.DataFrame(empty, columns=['column1', 'column2', 'column3'])
  ```

  

### Histogram

``` python
import matplotlib.pyplot as plt

plt.hist(df.similarity, bins=30)
plt.title(methods)
plt.ylabel('number of data')
plt.xlabel('similarity')
```



### Technique

- null을 이용한 선택적 값 입력(numpy bool에서는 미작동.)

```python
a['Attribute'] = a['A']*'A' + a['B']*'B' + a['C']*'C' + a['D']*'D'
```

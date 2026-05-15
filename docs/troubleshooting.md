## 2026.05.15
## 수치형 피처 str -> int/float 형변환

### 문제
1. 
df['discounted_price'] = (
    df['discounted_price']
        .str.replace('₹', '', regex=False)
        .str.replace(',', '', regex=False)
        .astype(int)
)
2. 
df['rating_count'] = (
    df['rating_count']
        .str.replace(',', '', regex=False)
        .astype(int)
)

이런 식으로 astype 과정에서 계속 오류 발생했는데 원인 파악 어려웠음.

### 원인
1. df.head()로 앞부분만 확인한 나머지, 가격/할인 피처에는 소수값이 존재할 수 있다는 것을 간과했음.
2. rating_count 피처에 결측치가 존재함을 모르고 형변환을 진행함.

### 해결
1. 가격/할인 피처는 모두 astype(float)로 수정
2. 결측치 처리


# Probability and Statistical Inference


## Chapter 1. Probability
## Chapter 1.1 Properties of Probability



## i = 시행횟수
## j = 시행 내 반복횟수

## n = 주사위 면 K
## count = 시행 횟수 변수

```Python

import pandas as pd
import random

save = pd.DataFrame()



K = 1
count = 100

for i in range(count):
       for j in range(6):
        try:
            n = K

            k = (1,2,3,4,5,6)

            if n > 6:
                raise ValueError

            else:
                save.loc[i,j] = random.choice(k)

        except Exception as ex:
            print("에러가 발생했습니다.", ex)
```

# 주사위를 6번 던져 한 번이라도 주사위 K면이 나올 확률

# 1이 단 한 번도 나오지 않은 시행 횟수
nonK = len(save[save.isin([K]).sum(axis=1)==0])

# 확률 계산 결과
print(1 - (nonK / count))

# 시행 결과 테이블
print(save)

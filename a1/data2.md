데이터 분석 연습 2
1904~2022 최고온도
  ```
  import csv
import random

import matplotlib.pyplot as plt

def get_temp_data():
    csv_file = open('sample2.csv', 'r', encoding='utf-8')
    data = csv.reader(csv_file)
    header = next(data)

    temp_data = []

    for line in data:
        temp = line[5]
        if temp != '':
            temp_data.append(float(temp))

    return temp_data


def display_chart(data):
    # plt.rc('font', family='Malgun Gothic')
    # plt.rc('axes', unicode_minus=False)
    # plt.title('년도별 최고 온도')

    plt.plot(data)

    plt.show()

def display_box():

    data1 = []
    data2 = []

    for i in range(20):
        data1.append( random.randint(1, 500))
        data2.append( random.randint(501, 1000))

    print(data1)
    print(data2)


    #print(np.percentile(data, 25))
    #print(np.percentile(data, 50))
    #print(np.percentile(data, 75))

    plt.boxplot([data1, data2])
    plt.show()
    ```
    실행 코드
    ```
      from qwe1 import get_temp_data
from qwe1 import display_chart
from qwe1 import display_box

temp_data = get_temp_data()
print(temp_data)
display_chart(temp_data)
#display_box()
```
![](https://github.com/yoonhunbin/data.analysis/blob/main/data1.png.png)

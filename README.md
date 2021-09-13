# Big Contest 수산biz

(연어)
## 1. 데이터 EDA
1. 데이터의 이상치 제거 -> IQR을 사용했는데 전체 데이터를 가지고 IQR을 한번 진행해 주었고, 그 이후 각 수입형태별 수입용도별로 IQR을 진행해 주었습니다.
2. Test 데이터를 맞추기 위해서는 시간별 데이터를 가지고 mapping을 시키는 방법을 사용
3. 그러기 위해서 week을 기준으로 수입용도, 수입형태, 제조국의 week별 평균을 데이터로 넣어줌
4. USD환율이 무역에서 영향이 있기 때문에 넣어주려고 했지만 target값과 단위 차이가 너무 심해서 log를 씌워서 데이터를 넣어줌
5. 배로 운송이 진행되기 때문에 유가 데이터가 필요하다고 생각했고 유가 데이터를 구할 수가 없어서 yfinance에서 WTI 주식을 전체 일자에 mapping을 시킨 다음에 7일씩 짤라서 평균을 넣어줌
6. target을 voting방법을 예측을 한 이후에 target의 moving average를 구해서 데이터를 다시 생성해주고 변수로 넣어준다.

## 2. 모델링
1. Voting을 이용해서 1차 예측을 진행
2. moving average 예측한 target값과 train의 target값으로 moving average columnn을 만들어 주고 다시 Voting regressor로 다시 예측을 진행했습니다.

# Big Contest 수산biz

## 1. 데이터 EDA
1. 데이터의 이상치 제거 -> IQR을 사용했는데 전체 데이터를 가지고 IQR을 한번 진행해 주었고, 그 이후 각 수입형태별 수입용도별로 IQR을 진행해 주었습니다.
2. Test 데이터를 맞추기 위해서는 시간별 데이터를 가지고 mapping을 시키는 방법을 사용
3. 그러기 위해서 week을 기준으로 수입용도, 수입형태, 제조국의 week별 평균을 데이터로 넣어줌
4. 단일모델, stacking, voting을 사용한 결과 RandomForestRegressor가 가장 잘 맞았다.
5. GridSearchCV를 사용해서 파라미터 최적화를 시행해 주었습니다.

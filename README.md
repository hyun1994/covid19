# Covid19
* EDA ipynb파일에 보이지 않는 이미지 추가
  * 도시 별 감염 비율 
  ![도시 별 감염 비율](https://user-images.githubusercontent.com/87411381/172416286-f1d8234b-e28b-4aad-9c63-7b0a3a737e3d.JPG)
  * 해외유입 도시 별 감염 비율
  ![해외유입 도시 별 감염 비율](https://user-images.githubusercontent.com/87411381/172416667-09f644ee-5bde-477a-bfd6-a41fe82dba1a.JPG)
  * 국내 첫 확진자 방문 경로
  ![국내 첫 확진자](https://user-images.githubusercontent.com/87411381/172421426-2acdccdc-ca74-45e9-8f33-6a9c75039271.JPG)
  * 외국인 방문 경로
  ![외국인 방문](https://user-images.githubusercontent.com/87411381/172421521-75fcfc09-4aa6-417f-9172-d117b425ba2e.JPG)

## EDA

- 데이터 출처
    - 출처1 : Dacon 코로나 시각화 대회 데이터
    - 출처2 : [https://ourworldindata.org/coronavirus/country/south-korea](https://ourworldindata.org/coronavirus/country/south-korea)
- 신천지 확진자가 없었다면 분석 내용
    - 외국인들의 자주 방문한 경로 시각화를 한 결과 병원(37%), etc(17%),대중교통(10%),음식점(10%),공항(10%)이 많은 비중을 차지하고 있음
    - 공항은 인천, 청주, 군산에서 확인 가능하지만 경북 청도군청의 위치에서 1명을 확인
    - 대중교통은 서울역과 부산에서 확인
    - 위의 시각화에서 외국인들의 주 이동경로는 수도권과 부산이므로 외국인 해외유입 확진자는 국내 해외유입 확진자보다 평균적으로 접촉횟수가 많아서 수도권과 부산에 영향을 미친다고 판단
    - 국내로 입국하는 인원들 중 병원을 여러곳 방문하는 기록이 많은 점을 보아 국내로 입국해서 병원을 가는게 이득이라고 생각할 정도록 외국인에 대한 병원 관련 복지가 좋아서 입국하는 외국인들에 대한 조치가 필요

## Modeling

- Model은 Tabnet으로 학습
- 전체 컬럼을 학습시켰을 때 R2 점수는 약 31%
- EDA에서 분류한 컬럼들로만 학습 시켰을 때 R2점수는 약 63%
- NaN값을 제거 후 데이터가 많이 줄어들어 학습 시켰을 때 오히려 R2점수는 오히려 하락함

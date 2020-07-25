---
    title : "[데이터 사이언스] 공공데이터 프로젝트"
     
    description : "공공데이터 프로젝트 과정"
    
    categories : 
        빅데이터
        
    tags :
        머신러닝
        데이터사이언스

    last_modified_at  : 2020-06-01
---

# 빅데이터 분석 

## 공공데이터 - taas 에서 제공하는 교통정보를 활용한 예측모델 만들기

* 입력값 : 사고유형 , 사고지역 , 발생건수 , 위도 , 경도 , 날씨 , 요일 , 시간대

* 예측값 : 사상자수 

* 사상자수 = 사망자수 + 중상자수 + 경상자수 + 부상자수

## 데이터 모델링 과정
pandas data frame을 통해 기본적인 데이터를 스케일링함.

matplotlib의 hist 함수를 사용해 시각화하려했으나, x축의 feature값을 지정하지못하여 적합한 함수가 아님을 인지, 구글링을 통해 

```python
df.plot(kind = 'bar')
```
함수를 발견 , 활용하여 시각화 실시

! 문제점 : 아직 x축의 값 즉 row 의 index를 임의값으로 변경하여 년도를 표현하는 방법을 찾지 못함. 이를 해결해야함.

## 다운받은 데이터를 적합한 형태로 변경

os.path.join을 통해 local 에 dataset 경로를 지정

!문제점 : 만약 SQL이나 다른 DB에 있을경우 이 경로를 어떻게 설정해야하는가?

pandas의 read_excel 함수를 활용하여 dataframe을 생성함.

만약 csv파일이라면 read_csv를 사용하면 됨.

## 궁극적인 문제점

* 내가 갖고있는 데이터는 매 사고가 발생했을 때 마다의 데이터가 아님. 이미 한번의 데이터 처리를 통해 통계화된 수치임. 이를 어떻게 활용해 원하고자하는 인공지능을 설계할 수 있을지 고민해봐야함.

-> 원래 내가 생각했던것은 통계화된 수치를 조합할 예정이었음. 하지만 이것은 결국 통계적 추론에 불과하다는 결론에 도달함. 인공지능을 보다 정확하고 강력하게 만들기 위해서는 매년 일어나는 매 사고 건수에 대한 데이터가 필요.

* 시각화에 대한 지식 부족으로인해 어떤 데이터를 어떻게 표현할지에 대한 정확한 감이 없음. 이부분은 금방 학습할 수 있을것으로 예상됨.

* commit을 조금 더 의미있고, 자주해야함. 혹여 문제가 생겼을 때 head포인터를 활용해서 그전으로 돌아가 트러블 슈팅을 하기 위함.

[[공공데이터프로젝트Github]](https://github.com/YangDongJae/MachineLearning_Log)

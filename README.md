# BERT를 활용한 속성별 음식점 리뷰 분석
**[ 23-1 졸업프로젝트 ]**

</br>

## 요약

Transformer 기반의 BERT를 fine-tuning하여 네이버의 한글 음식점 리뷰를 분석한다. 리뷰를 food, service, price 각각의 측면에서 해당 리뷰의 긍정/부정 여부를 분류하고, 그래프로 결과를 시각화한다. 결과적으로 한 음식점에 대한 만족도를 세 가지 측면에서 도출, 수치화 함으로써 여러 음식점과의 비교를 용이하게 한다.

</br>
</br>

## 연구 배경

- 2022년 1분기 네이버플레이스 별점 리뷰 폐지, 키워드 리뷰로 대체
- 음식점에 대한 평가를 바로 파악하기 어려움
- 여러 음식점을 서로 비교할 때 기준 척도가 없는 어려움

</br>
</br>

## 프로젝트 내용

#### BERT fine-tuning

| Aspect   | Train Loss | Validation Accuracy | Test Accuracy |
|----------|------------:|---------------------:|---------------:|
| Food  | 0.0148   | 0.8854 | 0.8750 |
| Service    | 0.0003   | 0.8958 | 0.9600 |
| Price| 0.0980   | 0.7875 | 0.8700 |
| Ambience| 0.0005   | 0.9063 | 0.8478 |


</br>

#### Attention 추출
BERT-base 모델의 마지막 layer의 모든 head에 대한 attention 값 평균을 구하고, attention 값이 높은 단어 순서대로 하이라이트를 주어 시각화했다.

![image](https://github.com/Eunjin3395/graduation_project/assets/114724403/780095df-f303-49d7-a750-cbc79ab1ec38)


![image](https://github.com/Eunjin3395/graduation_project/assets/114724403/9ef4d227-f520-4b60-9944-527158312455)


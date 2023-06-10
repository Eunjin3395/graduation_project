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
영어 리뷰 데이터로 BERT모델을 fine-tuning한 결과, 평균 89%의 정확도를 보임

| Aspect   | Train Loss | Validation Accuracy | Test Accuracy |
|----------|------------:|---------------------:|---------------:|
| Food  | 0.0148   | 0.8854 | 0.8750 |
| Service    | 0.0003   | 0.8958 | 0.9600 |
| Price| 0.0980   | 0.7875 | 0.8700 |
| Ambience| 0.0005   | 0.9063 | 0.8478 |

`Food: 1,415건, Service: 930건, Price: 400건, Ambience: 565건`


</br>

#### Attention 추출
BERT-base 모델의 마지막 layer의 모든 head에 대한 attention 값 평균을 구하고, attention 값이 높은 단어 순서대로 하이라이트를 주어 시각화

- 12 layer의 attention 시각화

![attention](https://github.com/Eunjin3395/graduation_project/assets/114724403/39bf62d9-e242-496c-a4a4-190c58aca6fb)

</br>

- Food, Service, Price 속성별 리뷰 문장의 attention 시각화

![image](https://github.com/Eunjin3395/graduation_project/assets/114724403/9575980c-9f79-400d-91be-66df2474bc13)

</br>

![image](https://github.com/Eunjin3395/graduation_project/assets/114724403/608f1fda-5f95-4be1-879f-40d2b21d9f4f)


</br>

![image](https://github.com/Eunjin3395/graduation_project/assets/114724403/ea84d2b1-4b20-4303-919f-49ab08902959)


</br>
</br>

#### 네이버플레이스 리뷰 테스트
네이버플레이스의 한글 리뷰 280건에 대한 BERT모델의 분류 정확도

| Aspect   | Test Accuracy |
|----------|------------:|
| Food  | 0.9625   |
| Service    | 0.8400   |
| Price| 0.8800   |

</br>
</br>

#### 실제 음식점 리뷰 분석
리뷰가 1,000건 이상 달려 있는 음식점 세 곳의 리뷰 수집 후, 속성별 분석 결과

<!-- ![n1](https://github.com/Eunjin3395/graduation_project/assets/114724403/adf42407-baaf-451b-9b31-4c3c4414aad8) -->

<img src="https://github.com/Eunjin3395/graduation_project/assets/114724403/adf42407-baaf-451b-9b31-4c3c4414aad8" alt="n1" width="300px" height="500px">


</br>

<!-- ![n2](https://github.com/Eunjin3395/graduation_project/assets/114724403/2b5cebbb-de5c-4617-98c2-4e993016e20e) -->

<img src="https://github.com/Eunjin3395/graduation_project/assets/114724403/2b5cebbb-de5c-4617-98c2-4e993016e20e" alt="n2" width="300px" height="500px">

</br>

<!-- ![n3](https://github.com/Eunjin3395/graduation_project/assets/114724403/cc772f18-2f55-48dc-894c-9dacded9ae56) -->

<img src="https://github.com/Eunjin3395/graduation_project/assets/114724403/cc772f18-2f55-48dc-894c-9dacded9ae56" alt="n3" width="300px" height="500px">

</br>
</br>
</br>

## 프로젝트 내용

- BERT를 fine-tuning함으로써 맛, 서비스, 가격 속성 각각에 대한 감정 분류
- BERT모델에서 attention을 추출해 모델이 주목하고 있는 단어 표현 도출
- 특정 음식점 네이버 리뷰의 맛, 서비스, 가격 측면 만족도 확인

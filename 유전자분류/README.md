# Recap

## 22.12.31.
- 베이스라인 데이터 다운로드
- Data 확인
- Randomforest Parameter 수정 

## 23.1.1.
- seed = 42로 고정 후 파라미터 AB테스트 실시
- Private Score 0.9622에서 0.942, 0.952로 감소
- DecisionTree 코드 추가

## 23.1.2.
- Decision Tree 기본 Parameter 는 0.93로 감소
- 비교군에서 B일 경우 예측값 C가 증가할수록 정확도가 감소
- 실제 B를 예측하는 것이 분석의 관건이라고 판단됨

## 23.1.5.
- Scikit-learn을 통한 분석 실시
- Private Score 0.9622의 예측값을 true(test)로, 새로운 기법 예측값을 pred로 할당함
  - 기존보다 B 예측값이 증가하는 모델을 찾기로 함.
- KNN 수행 - str 변수를 숫자로 된 값으로 변환함
  - Private Score 0.9622로 증가(Randomforest 비교모델과 차이없음)
  - B -> C 1개 / C -> B 2개
- 
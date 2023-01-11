# Recap

## 22.12.31. RandomForest
>
> ### 베이스라인 데이터 다운로드
>- Data 확인
>- Randomforest Parameter 수정 

## 23.1.1. ~ 23.1.2. DecisionTree
>### seed = 42로 고정 후 파라미터 AB테스트 실시
>### Private Score 0.9622에서 0.942, 0.952로 감소
>### Decision Tree 기본 Parameter 는 0.93로 감소
>  - 비교군에서 B일 경우 예측값 C가 증가할수록 정확도가 감소
>  - 실제 B를 예측하는 것이 분석의 관건이라고 판단됨

## 23.1.5.~ Scikit-Learn Lib
>### RandomForest의 예측값(Private Score 0.9622)을 true(test)로, 새로운 예측값을 pred로 할당함
>### 기존보다 B 예측값이 증가하는 모델을 찾기로 함.
> ### KNN
>    - str 변수를 숫자로 된 값으로 변환함
>    - Private Score 0.9622(RandomForest와 동일)
>    - B -> C 1개 / C -> B 2개
> ### LogisticRegression
>    - Private Score 0.9814로 증가
>    - B -> C 2개 / C -> B 1개
>    - B의 예측수 증가가 정확성과 항상 비례하진 않는다고 판단됨
> ### Naive bayes
>    - Private Score 0.9719
>    - B -> C 1개
> ### DecisionTree Another Parameter
>    - Private Score 0.9107
>    - B -> C 6개
> ### RandomForest Another Parameter
>    - Private Score 0.9622
>    - Randomstate 등 Parameter 조절
>    - 유의미한 변화 없음
> ### GradientBoosting
>    - Private Score 0.9622
>    - Randomstate 등 Parameter 조절
>    - 유의미한 변화 없음
> ### LogisticRegression Another Parameter
>    - 변화없음
>    - value값의 갯수 말고 개별적으로 변화가 있는지를 체크함
>    - {3, 14, 60, 103, 119, 126, 162}가 반복적인 C값 조절에서 변동되는 데이터로 보임 
>    - 이 중에 답이 있을 거라 생각하고 테스트 진행
>    - 기존 선형모델의 예측값을 test셋으로 놓고 AB테스트
>    - 126 B->C : Private Score 변화없음(정답이라고 가정)
        
## 23.1.8. ~ 23.1.9. XGBoost, LGBM + Optuna
> ### 정확도가 0.16 수준
> ### Drop
# Battery-Diagnostics-Study
공업사  경험을 바탕으로 한 자동차 배터리 진단 및 분석 기록

# 프로젝트 목표
공업사에서 수집한 자동차 배터리 진단 데이터를 이용한 SOH(State of Health)와 주요 파라미터간의 관계 분석 및 NASA 데이터와 비교, 배터리 열화 특성을 이해하고 등가회로 기반 시상수와의 연관성 탐색

# 프로젝트 구조
Battery-Diagnostics-Study/
data/
notebooks/
docs/
README.md

# Dataset
## 1. 공업사 실제 차량 배터리 데이터

- Voltage
- Internal Resistance
- CCA
- SOH

## 2. NASA 배터리 데이터

- NASA Ames Prognostics Center
- Li-ion Battery Aging Dataset
- Charge
- Discharge
- Impedance Cycle

# 분석 흐름

공업사 데이터 EDA

↓

NASA 데이터 EDA

↓

공업사 ↔ NASA 비교

↓

가설 검증

↓

RC 등가회로 기반 해석

↓

Feature 선정

↓

SOH 예측 모델

↓

시나리오 기반 예측

↓

결론

# 가설
공업사에서 측정 가능한 내부저항, CCA, 전압, 온도 데이터를 이용하면 RC 등가회로 기반 배터리 특성을 간접적으로 추정할 수 있으며, 이를 통해 배터리 SOH 및 잔존 수명을 예측할 수 있을 것이다.
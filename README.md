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
## 1. Workshop Battery Dataset

- 공업사에서 수집한 실제 차량 배터리 데이터
- 변수
    - Voltage
    - Internal Resistance
    - CCA
    - SOH

## 2. NASA Battery Dataset

- NASA Ames Prognostics Center
- Li-ion Battery Aging Dataset
- Charge
- Discharge
- Impedance Cycle

# 분석 흐름

Work battery Data

↓

EDA

↓

NASA Charge

↓

NASA Discharge

↓

Capacity

↓

SOH

↓

Impedance

↓

Comparison
↓
Conclusion

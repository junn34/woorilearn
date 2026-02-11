# 우리런 (WeLearn)

실제 금융 업무 흐름을 기반으로 설계된 시나리오형 금융 학습 플랫폼
단순 UI 시뮬레이션이 아닌, 실제 백엔드 API와 데이터 처리 구조를 기반으로 동작하는 금융 체험 서비스

<img width="368" height="507" alt="Image" src="https://github.com/user-attachments/assets/26ca5f0e-115a-4d08-884a-77b7cecfa14c" />

# ● Overview

우리런은 금융 서비스 이용 경험이 부족한 사용자가
위험 부담 없는 가상 환경에서 송금·계좌조회·자동이체 등의 금융 업무를 직접 체험할 수 있도록 설계된 플랫폼입니다.

본 프로젝트는 기능 구현보다 금융 서비스의 신뢰와 무결성을 기준으로 설계하는 것에 초점을 두었습니다.

# ● Core Features
### 1. 시나리오 기반 금융 체험

실제 금융 업무 흐름을 반영한 단계별 시나리오 구성

사용자의 선택에 따라 상태가 변화하는 구조

송금, 계좌조회, 자동이체 등 주요 금융 프로세스 구현

### 2. 실제 API 기반 데이터 처리

모든 사용자 행동은 실제 DB 트랜잭션을 통해 처리

단순 프론트엔드 시뮬레이션이 아닌 실제 서비스와 유사한 처리 흐름

### 3. 포인트 환전 시스템

시나리오 완료 시 포인트 지급

포인트는 플랫폼 내 신규 개설 계좌로만 환전 가능

재화 성격 데이터를 고려한 무결성 보장 설계 적용

# ●  Service Architecture
민감 데이터 보호를 고려한 하이브리드 아키텍처 기반 운영 구조

<img width="928" height="363" alt="Image" src="https://github.com/user-attachments/assets/e7a4bab8-82d1-4abe-9f32-e0282dd6dd0e" />

# ●  Design for Reliability
### 1. 동시 요청 환경에서 단일 결과를 보장한 데이터 설계

포인트 지급/환전 과정에서 동시 요청 시 중복 지급 가능성 발견

비관적 락(Pessimistic Lock) 적용

UNIQUE 제약 조건을 통한 중복 트랜잭션 사전 차단

트랜잭션 경계 명확화로 단일 결과 보장

동시 요청 환경에서도 포인트 무결성 유지

### 2. 민감도 기반 캐시 분리 전략

조회 빈도가 높은 비민감 데이터는 캐시 적용

계좌 정보·재화 관련 데이터는 캐시 제외

성능 개선과 보안 리스크를 동시에 고려한 구조

### 3. 운영 리스크를 줄이기 위한 CI/CD 구조

Jenkins 기반 자동 배포 파이프라인 구축

개발/운영 환경 분리

온프레미스–클라우드 분리 설계로 민감 정보 보호

반복 수동 배포 제거로 배포 리드타임 단축

# ● Testing & Stability

상태 변경이 수반되는 핵심 로직 중심 테스트 설계

<img width="908" height="398" alt="Image" src="https://github.com/user-attachments/assets/bccbec70-70bc-4eee-83b7-8741655e5f0b" />

● Tech Stack

<img width="870" height="356" alt="Image" src="https://github.com/user-attachments/assets/4ee0f30c-9941-46ee-a5c5-cd6a7ea8cfbd" />


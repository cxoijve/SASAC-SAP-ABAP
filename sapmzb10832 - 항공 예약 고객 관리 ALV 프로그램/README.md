# 항공 예약 관리 ALV 프로그램 (SAPMZB10832)

## 주요 기능

1. 기본값 설정

   - 2달 전 1일자, 한달 후 일자 등 예약일 기본값 자동 설정
   - Function Module(RP_CALC_DATE_IN_INTERVAL)로 처리

2. ALV 필드 변경

   - `CUSTTYPE`, `CLASS` 필드는 NO_OUT 처리
   - 각 TEXT 필드 추가 후 ALV 출력

3. ALV 데이터 정렬

   - 최근 비행일자별, 좌석등급별, 가장 빨리 예약한 순으로

4. 예약 정보 조회 및 표시

   - 고객명, Flight Class Text, Customer Type Text 취득
   - 출발전예약일수 계산 -> Function Module FIMA_DAYS_AND_MONTHS_AND_YEARS) 활용

5. 조건부 데이터 삭제
   - 고객번호 조건 입력 시 DELETE <itab> 기법 적용

## 추가 조건

1. 이후 추가 조건 개발 환경에 맞게 변경

   - 구조체(ZSB103304) 필드 추가

2. Function Module/Domain 재사용성 강화

   - `GET_DOMAIN_VALUES`에서 한 번만 값을 받아 internal table로 관리
   - 반복 호출 대신 필요 시 조건 활용하여 효율적으로 데이터 표시

3. 항공사 및 가격 정보 표시

   - 통화 단위 잘 나오도록 설정
   - `SFLIGHT`, `SBOOK` 조인 후 원가 정보 취득 (SFLIGHT에서 PRICE 정보 읽어옴)
   - 할인금액 표시
     - 통화 단위가 다르다면 무조건 0원 (SFLIGHT-CURRENCY와 SBOOK-LOCCURKEY 참고)

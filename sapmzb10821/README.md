# SAPMZB10821

- [B10] ALV 3 – 예약 현황 Field Catalog, Refresh_table_display

## 기능 요약

- **예약 현황 조회 및 조건별 필터링**

  - 항공사, 연결번호, 기간 등 필수조건 설정
  - CLASS(좌석등급)는 Range Variable을 WHERE 조건에 사용
  - CUSTTYPE(고객유형)은 내부테이블 DELETE 방식으로 필터링

- **데이터 처리 절차**

  1. Table SBOOK에서 기본 레코드 데이터 취득
  2. '2달 이전 예약' 필드 추가
     - 두달 전에 예약 : 'X' 표시
     - 그렇지 않은 경우 : 초기값('')로 표시
  3. 예약현황, 예약일자, 고객번호 등 요구되는 필드 순서/명칭으로 출력

- **도메인 값 텍스트 변환 처리**

  - 좌석등급, 고객타입 등은 코드 대신 텍스트필드로 화면 표시
  - 표준 Function Module `GET_DOMAIN_VALUES` 활용

- **조건 미선택 시 전체 데이터 표시**

  - CLASS/CUSTTYPE 값 미입력시, 모든 레코드 노출

- **표준 날짜 함수 활용**
  - `RP_LAST_DAY_OF_MONTHS`, `RE_ADD_MONTH_TO_DATE` 등

## 예외사항 체크 (예외 아이콘, 색상 적용 로직 - 진행중)

- 예약일자보다 항공일자가 큰 경우: Red Icon
- 고객타입 다를 경우: Yellow Icon (현재 고객타입은 하나 - 생각해보기)
- 이외: Green Icon

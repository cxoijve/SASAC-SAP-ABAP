# ALV Double Click event

- 기내식 조회 프로그램
  <img width="909" height="713" alt="img 1" src="https://github.com/user-attachments/assets/81f0206e-97ce-4fba-b732-f9e64402edd3" />
  <img width="909" height="713" alt="img 2" src="https://github.com/user-attachments/assets/ee78c6f5-9c90-4605-a3ad-d11662252572" />

### 1. 예약현황 조회

- 조건:
  - Airline, Flight Number, Date 등 조회
  - Booking Number, Customer Number는 입력하지 않으면 조건에서 제외 (Range Variable 또는 DELETE 문 활용)
  - 기본값은 Airline=KA, Flight Number=17, Date=2025.08.10로 설정
- 데이터:
  - 예약번호, 고객번호, 고객명, 고객구분, 좌석등급, 항공일자, 항공편, 항공사 등 조회

### 2. ALV List Field 추가 및 숨김

- 필드 텍스트: Table의 Data Element(예: SBOOK, SCUSTOM, SCARR) 이름 그대로 사용

- 고객번호, 고객구분, 좌석등급, 항공사코드 등은 ALV Field Catalog의 NO_OUT 처리

### 3. 검색조건 UI

- 좌석등급(First/Business/Economy):
  - Radio Button(또는 Check Box) 구현

### 4. 기내식 조회 화면

- Screen 100:
  - Application Toolbar에 ‘기내식 조회’ 버튼 추가
- Screen 200으로 이동:
  - Screen 100 Application Toolbar의 '기내식 조회' 버튼과 함께 예약 리스트 ALV에서 해당 행을 더블클릭해도 화면 200으로 이동되도록 이벤트 핸들러 구현
  - 기내식 정보는 Table SMEAL 등 참고하여 구현

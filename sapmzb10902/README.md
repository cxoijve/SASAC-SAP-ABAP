# 항공사 담당자 관리 프로그램 (CRUD)

## 1. 조회 조건 (Screen 0100)
<img width="909" height="713" alt="img1" src="https://github.com/user-attachments/assets/41c5176a-3060-4002-9ee6-c2261ffc4995" />
<img width="909" height="713" alt="img2" src="https://github.com/user-attachments/assets/ebac6ae9-d3a5-4f16-b0ce-64e13cec6830" />

- 기본값: 담당 시작일 ~ 한 달 이후 기간 내 담당자 조회
- 담당자(사원번호) 필수 입력, 담당자명은 사원번호 입력 시 자동 설정
- ALV 리스트 정렬: 담당자별 최신 담당일 순

## 2. 담당자 등록 화면 (Screen 0200) - INSERT
<img width="909" height="713" alt="img3" src="https://github.com/user-attachments/assets/8233ab93-89cc-45a3-9a2c-6880f31558bc" />
<img width="909" height="713" alt="img4" src="https://github.com/user-attachments/assets/b50f2a85-70e7-4b20-bc4f-c0483a9f0788" />

- 100번(ALV 리스트) 화면의 Application Toolbar에 ‘담당자 등록’ 버튼 클릭 시 Screen 0200으로 이동
- Screen 0200에는 ‘신규 담당자 등록’ 버튼 포함
- 필수 입력: 담당자, 담당일(기본값: 현재일~9999.12.31), 항공사, 항공편
- 입력 후 Enter 치면 담당자 및 항공편 정보 표시
- 항공사별 기존 등록 담당자 중복 등록 시 메시지 표시하여 등록 제한
- 문제 없으면 테이블에 데이터 INSERT 후 리스트 화면으로 이동 및및 성공 메시지 표시

## 3. 담당자 변경 화면 (Screen 0300) - UPDATE

- 레코드 선택 후 버튼 클릭 시 Screen 0300으로 이동
- 항공사/항공편 정보는 조회 모드, 담당자는 필수 입력
- 입력 후 Enter → 담당자명 표시
- 동일 담당자 사번인 경우에는 담당일만 변경
  - <img width="909" height="713" alt="img5" src="https://github.com/user-attachments/assets/217d6fdd-e2ff-4dbb-b546-880eaa07915a" />
  - <img width="949" height="669" alt="img6" src="https://github.com/user-attachments/assets/5eab9738-58eb-4157-8d80-b8a2057c4751" />

- 신규 담당자가 기존 등록자와 다를 경우, 기존 담당자 종료일(ENDDA)을 현재일로 변경하고 신규 담당자 INSERT
  - <img width="883" height="697" alt="img7" src="https://github.com/user-attachments/assets/d37c1f55-3f05-499d-89e8-24d1f1724a4c" />
  - <img width="961" height="651" alt="img8" src="https://github.com/user-attachments/assets/748936ec-35d5-4ff6-9e98-6e07948bad59" />
  - <img width="890" height="699" alt="img9" src="https://github.com/user-attachments/assets/546e9cca-332c-4a61-b2dc-dd5495c618aa" />

- 완료 시 ALV 리스트 화면으로 이동 및 변경 완료 메시지 표시

## 4. 담당자 상세조회 화면 (Screen 0400)
<img width="890" height="699" alt="img10" src="https://github.com/user-attachments/assets/d7012efe-9422-4692-99c7-64b665064300" />
<img width="971" height="579" alt="img11" src="https://github.com/user-attachments/assets/0009e36d-ea6a-42b7-b1e1-28f3c7b71758" />

- 400번(ALV 리스트) 화면의 Application Toolbar에 ‘담당자 상세조회’ 버튼 추가
- 레코드 선택 후 버튼 클릭 시 Screen 0400으로 이동
- 담당자 및 항공편의 상세 정보 화면 제공

## 5. UI 구성 및 팝업(서브스크린)
<img width="603" height="693" alt="img12" src="https://github.com/user-attachments/assets/a74bb71c-68ee-4886-90b2-902ef8f74dca" />
<img width="609" height="693" alt="img13" src="https://github.com/user-attachments/assets/b35793b8-27d7-4890-b702-715a5bac815e" />

- 더블클릭 이벤트 발생 시 각각의 상세 정보를 서브스크린(팝업)으로 표시
- 서브스크린 0101: 부서명 더블클릭 시 부서코드, 부서명, 내선번호를 팝업형태로 보여줌
- 서브스크린 0102: 항공사명 더블클릭 시 항공사코드, 항공사명, 통화 정보를 팝업형태로 표시

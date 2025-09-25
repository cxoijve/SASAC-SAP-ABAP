# 전표 조회 및 관리 프로그램
### 조회 화면(Screen 0100)
<img width="1024" height="833" alt="img1" src="https://github.com/user-attachments/assets/067f0063-623d-4d02-af9d-5d714c3fe2ab" />

- 버튼 클릭 시 ALV EDIT 기능 구현
  - <img width="1014" height="829" alt="img1-2" src="https://github.com/user-attachments/assets/0f193510-d00b-475b-a64c-df8cdd6ab6b3" />
  - <img width="1014" height="829" alt="img1-3" src="https://github.com/user-attachments/assets/f37286fd-7e19-4d4d-8755-07bf4f3de58e" />

- 대량 전표 생성을 위한 엑셀 업로드 기능 추가
  - CALL TRANSACTION 'ZRBSSFI01'. 구문을 통해 엑셀 업로드 프로그램으로 이동  ([zrbssfi01 - 전표 생성 BDC 프로그램](https://github.com/cxoijve/SeSAC_PROJ/tree/main/zrbssfi01%20-%20%EC%A0%84%ED%91%9C%20%EC%83%9D%EC%84%B1%20BDC%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8))
    - <img width="1033" height="837" alt="img 13" src="https://github.com/user-attachments/assets/a20ce219-e61d-4991-b1ff-422a363f8a25" />

- 반제(Clearing) 처리를 위한 기능 추가
  - CALL TRANSACTION 'ZSSFI02'. 구문을 통해 반제 프로그램으로 이동
    - <img width="1025" height="831" alt="img11" src="https://github.com/user-attachments/assets/78d96aa6-f153-4d29-835f-4e92fcfcc54e" />


### 상세조회 화면(Screen 0300)
- 조회 결과 화면에서 한 행 선택 후 상세조회 클릭
  - <img width="1024" height="833" alt="img2" src="https://github.com/user-attachments/assets/0dd2cc76-be34-46d8-9dea-5837d2bf6540" />
-  선택한 헤더-라인아이템 정보 상세조회
  - <img width="958" height="674" alt="img3" src="https://github.com/user-attachments/assets/441e75d5-3b8f-42d4-a185-790a24dc3a85" />

### 생성 화면(Screen 0200)
- 조회 화면에서 생성 클릭
  - <img width="1014" height="829" alt="img4" src="https://github.com/user-attachments/assets/ece739c6-932a-43c9-a87f-f6605961e69e" />

- 회계부서 사원만 나오도록 Search Help 출력
  - <img width="948" height="721" alt="img5" src="https://github.com/user-attachments/assets/98dac132-4d30-492c-8edb-206983e13150" />

- 헤더 정보 필수값 입력 후 라인아이템 추가
  - <img width="944" height="955" alt="img6" src="https://github.com/user-attachments/assets/4033c688-0094-4947-a30e-79a944bb8f72" />

- 추가 버튼 클릭 시 라인아이템 정보 입력 팝업
  - <img width="1103" height="730" alt="img7" src="https://github.com/user-attachments/assets/dc40a279-7720-461a-acc8-7dd1d8dfac45" />

- Enter 기능의 '입력 완료' 버튼 구현
  - <img width="1093" height="719" alt="img8" src="https://github.com/user-attachments/assets/4a3e0b4c-0084-40ba-af28-ff75e22794c0" />

- 입력된 정보 저장 기능의 체크 버튼 구현
  - <img width="1094" height="713" alt="img9" src="https://github.com/user-attachments/assets/645e1201-4869-4796-8b24-0b29954558b4" />

- 라인아이템 정보가 ALV에 갱신되고 Dr/Cr 총액 산정
  - <img width="946" height="711" alt="img10" src="https://github.com/user-attachments/assets/de26c578-f59b-41bc-9afb-13443a9ed42f" />

- 상계처리 로직 구현
  - <img width="940" height="950" alt="img11" src="https://github.com/user-attachments/assets/6dd0d66f-e541-4c75-95af-d4cb113341f0" />
  - <img width="941" height="717" alt="img12" src="https://github.com/user-attachments/assets/d080251a-28a5-4992-9d37-d3a4d2e9c62f" />

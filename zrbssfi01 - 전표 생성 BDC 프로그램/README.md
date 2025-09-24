# 엑셀 업로드 및 BDC 전표 생성 프로그램

- Test용 SAP_FI_BDC.xlsx 파일 업로드 후 실행(F8)
  - <img width="681" height="119" alt="IMG 1" src="https://github.com/user-attachments/assets/400b97fe-e0b7-421f-9dea-f7b330f19f04" />
- ALV로 데이터 입력값 시각화
  - <img width="1374" height="383" alt="IMG 2" src="https://github.com/user-attachments/assets/c84744bc-3afc-46a2-bc08-ea69d0d08124" />
- MODE 'N'로 BDC 실행 후 모든 전표 생성 완료! (이후 전표 조회 및 관리 프로그램으로 이동)
  - <img width="1027" height="833" alt="IMG 3" src="https://github.com/user-attachments/assets/d9961fd0-780d-4f4b-be7a-b978ce99b55d" />

### 개요

- 헤더-아이템으로 구성된 전표 대량 데이터를 SAP BDC 방식을 통해 자동으로 전표 입력 및 생성하는 프로그램
- GitHub에 함께 공개된 벤더마스터 CRUD 프로그램과의 차이점 (sapmzssfi01 - 전표 조회 및 관리 프로그램)

전표 조회 및 관리 프로그램: 사용자 대화형 입력/수정을 위한 CRUD 프로그램
본 BDC 프로그램(zrbssfi01): 엑셀 기반 대량 등록 자동화 BDC 프로그램

### 주요 기능

1. 엑셀 업로드

- ALSM_EXCEL_TO_INTERNAL_TABLE 함수를 이용해 엑셀 파일을 인터널 테이블(LT_ALSMEX)에 변환 저장
- DDIF_FIELDINFO_GET을 활용하여 데이터 테이블 구조 필드 정보(LT_DFIES) 조회
- LT_ALSMEX와 LT_DFIES 정보를 바탕으로 엑셀 각 셀 데이터를 구조체(GS_EXCEL) 필드에 동적 할당하여 전표별 인터널 테이블(GT_EXCEL) 생성

2. BDC 입력 및 전표 처리 (SET_BDC FORM)

- GT_EXCEL를 반복하면서 전표 헤더와 아이템을 구분해 화면별 BDC 데이터 생성
- 헤더는 HFLAG='X' 조건으로 스크린 0100, 0200에서 입력 처리
- 아이템은 금액(DEBIT, CREDIT) 및 계정(GLACC) 필드의 특수문자(콤마, 소수점)를 제거 후 문자형으로 변환하여 분개 스크린 0210에서 입력
- 아이템 마지막(EFLAG='X')에 도달하면 최종 등록 스크린(0200, '=INSERT')을 호출하여 전표 생성
- 최종 생성 후 해당 BDC 데이터로 CALL TRANSACTION 실행하고 BDC 입력 테이블 초기화

3. 메시지 처리

- 전표 등록 중 발생하는 SAP 메시지를 수집해 출력 가능(현재 주석 처리 상태)

### 주의사항

1. 데이터 타입

- CURR 타입 금액 필드는 BDC에 문자열로 전달해야 오류 방지함.
- 금액 값을 BDC에 넘기기 전에 소수점(.) 및 콤마(,)를 제거하고 문자형으로 변환하는 작업 필수
- ABAP 정규식 REPLACE ALL OCCURRENCES OF REGEX '[^0-9]' 구문을 사용하여 금액 필드 내 숫자가 아닌 모든 문자를 제거함.

2. 헤더-아이템 관계

- 엑셀 업로드 데이터는 헤더와 해당 아이템 구분용 플래그(HFLAG, EFLAG) 필요.
- 헤더 입력 후 해당 아이템을 순차 입력, 마지막 아이템에서 전표 최종 생성.

3. 성능 및 안정성

- 대용량 데이터 처리 시 BDC 호출 횟수 및 트랜잭션 실행 주의.

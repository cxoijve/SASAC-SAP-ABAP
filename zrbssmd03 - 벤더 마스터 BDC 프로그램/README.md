# BDC Excel Upload & Vendor 등록
<img width="707" height="128" alt="img1" src="https://github.com/user-attachments/assets/7871264e-4283-483e-95af-eeea7d27b743" />
<img width="943" height="483" alt="img2" src="https://github.com/user-attachments/assets/6a6ac8c1-2b75-42d1-a133-2c4bf0c54981" />
<img width="666" height="121" alt="img3" src="https://github.com/user-attachments/assets/c1c47551-8a75-402e-83ab-9133e881662b" />
<img width="685" height="152" alt="img4" src="https://github.com/user-attachments/assets/a0c5405a-af79-49ab-ab3e-ca61a7033457" />
<img width="1094" height="754" alt="img5" src="https://github.com/user-attachments/assets/82ce43d9-c995-4dd4-a1e8-d194ad796949" />

## 개요

- 대량 데이터를 한번에 입력하기 위한 BDC 자동화 프로그램
- GitHub에 함께 공개된 벤더마스터 CRUD 프로그램과의 차이점
  ([sapmzssmd03 - 벤더 마스터 CRUD 프로그램](https://github.com/cxoijve/SeSAC_PROJ/tree/main/sapmzssmd03%20-%20%EB%B2%A4%EB%8D%94%20%EB%A7%88%EC%8A%A4%ED%84%B0%20CRUD%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8))

  - 벤더 마스터 프로그램: 사용자 대화형 입력/수정을 위한 CRUD 프로그램
  - 본 BDC 프로그램(zrbssmd03): 엑셀 기반 대량 등록 자동화 BDC 프로그램

## 주요 기능

- 엑셀 업로드: 지정된 템플릿 형태의 엑셀 파일 데이터를 내부 테이블(`GT_EXCEL`)에 적재
  - Test용: SAP_VENDOR_DATA.xlsx
- 데이터 매핑: 엑셀 데이터 → 화면 필드(`ZSSSMD0303-*`)로 변환
- BDC 처리: `CALL TRANSACTION 'ZSSMD03'`로 트랜잭션 자동 실행 (Mode 'N')
- 메시지 로그: 실행 중 발생하는 메시지를 사람이 읽을 수 있는 문장으로 변환하여 출력

## 실행 절차

1. 프로그램 실행 (`ZRBSSMD03`)
2. Selection-Screen에서 업로드할 엑셀 파일 경로 입력
3. 실행(F8) 시 엑셀 데이터를 내부 테이블에 적재
4. 각 행마다 BDC 세션 생성 후 `ZSSMD03` 트랜잭션 호출
5. 실행 결과 메시지를 콘솔에서 확인

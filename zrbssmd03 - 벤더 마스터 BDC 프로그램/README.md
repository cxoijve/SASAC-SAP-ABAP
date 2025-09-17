# BDC Excel Upload & Vendor 등록

## 개요

- 대량 데이터를 한번에 입력하기 위한 BDC 자동화 프로그램
- GitHub에 함께 공개된 벤더마스터 CRUD 프로그램과의 차이점
  (경로: https://github.com/cxoijve/SeSAC_PROJ/tree/main/sapmzssmd03%20-%20%EB%B2%A4%EB%8D%94%20%EB%A7%88%EC%8A%A4%ED%84%B0%20CRUD%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8)
- 벤더 마스터 프로그램: 사용자 대화형 입력/수정을 위한 CRUD 프로그램
- 본 BDC 프로그램: 엑셀 기반 대량 등록 자동화 BDC 프로그램

## 주요 기능

- 엑셀 업로드: 지정된 템플릿 형태의 엑셀 파일 데이터를 내부 테이블(`GT_EXCEL`)에 적재
- 데이터 매핑: 엑셀 데이터 → 화면 필드(`ZSSSMD0303-*`)로 변환
- BDC 처리: `CALL TRANSACTION 'ZSSMD03'`로 트랜잭션 자동 실행 (Mode 'N')
- 메시지 로그: 실행 중 발생하는 메시지를 사람이 읽을 수 있는 문장으로 변환하여 출력

## 실행 절차

1. 프로그램 실행 (`ZRBSSMD03`)
2. Selection-Screen에서 업로드할 엑셀 파일 경로 입력
3. 실행(F8) 시 엑셀 데이터를 내부 테이블에 적재
4. 각 행마다 BDC 세션 생성 후 `ZSSMD03` 트랜잭션 호출
5. 실행 결과 메시지를 콘솔에서 확인

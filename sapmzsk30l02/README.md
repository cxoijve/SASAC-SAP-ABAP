### ABAP 기내식 신청 프로그램

<img width="1134" height="1032" alt="image" src="https://github.com/user-attachments/assets/c4be48e5-d702-4f4a-994c-4ac6cc55e31b" />
<img width="1134" height="1032" alt="image" src="https://github.com/user-attachments/assets/bbff1be7-4e04-451f-944d-83268822344c" />

(완료) 1단계
- 필수 조건: 항공사, 항공편, 날짜
- 옵션 조건: 예약번호, 고객번호 (입력 시만 필터)
- 취소된 예약은 조회 제외
- 조건 입력 후 Search 버튼 클릭 시 예약 리스트 조회(ALV)

(예정) 2단계
- 기내식 신청 현황 테이블(ZTSK30REQ) 생성
- Key: 항공사, 항공편, 날짜, 예약번호, 신청일
- 필드: 종료일, 기내식 메뉴번호, 신청상태(A:미신청, B:신청완료, C:신청취소)
- 하루 한 번만 신청 가능, 중복 시 기존 신청 취소 후 새 신청 추가

(완료) 3단계
- ALV 리스트에 신청상태 필드 추가(드롭다운으로 상태 선택)
- 선택 상태에 맞는 예약만 조회
- 미신청 상태 시 기내식 신청 내역 없는 예약도 포함 조회

- 이후 단계도 진행 보완 예정

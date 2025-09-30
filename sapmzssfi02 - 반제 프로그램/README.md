# 반제 프로그램

### 조회 화면(Screen 0100)

- Radio Button 구현

  - <img width="753" height="189" alt="img1" src="https://github.com/user-attachments/assets/04b48534-b448-4c80-b0b7-13ea7e0fd2e4" />

- AP/AR 선택 화면

  - <img width="735" height="196" alt="img1" src="https://github.com/user-attachments/assets/afbd5c48-1893-4077-947e-ac004a5c56d0" />

- 지급(AR) 처리 화면

  - 송장검증IV 정보를 모두 불러온 다음, AR 미결 항목인 하나의 행만 선택 가능
    - <img width="960" height="550" alt="img2" src="https://github.com/user-attachments/assets/7e2953d4-5a6f-4577-879a-66dc221c6303" />

- 선택한 송장검증IV 레코드에 해당하는 FI 전표 헤더-라인아이템 정보를 보여준 다음,
  '지급' 버튼을 누르면 지급 전표 생성됨(두 번 누르면 에러메세지 출력)

  - <img width="775" height="955" alt="img3" src="https://github.com/user-attachments/assets/a6439d3b-f0c9-4597-82fc-34b71b0bb418" />

- '미결항목처리' 버튼 누르면 반제 처리 완료(클리어링)

  - <img width="768" height="959" alt="img4" src="https://github.com/user-attachments/assets/7dc76f7d-62a6-4aab-ad9a-77c67470dac7" />

- 반제 처리 완료 후, 송장검증IV에 지급 전표번호와 지급 회계연도 정보 UPDATE!
  - <img width="952" height="955" alt="img5" src="https://github.com/user-attachments/assets/cde62ffa-7197-40f8-a2cc-04758ac2aa42" />

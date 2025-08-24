# ALV Deep Structure & Cell Color

- 자재 현황 프로그램
<img width="682" height="543" alt="img1" src="https://github.com/user-attachments/assets/338d9604-0cc1-4b42-a97a-2f8bed8a665e" />


1. ALV Grid Cell-Color 표시: 특정 조건(예시: 가격 등)에 따라 셀 색상 변경 구현
2. 코드 내 deep structure 사용

- Deep Structure 선언 부분:
    - zsb105002는 자재 구조, it_col은 cell color 정보
````abap
DATA: BEGIN OF gs_mat.   "deep structure 구조
    INCLUDE TYPE zsb105002.
DATA: it_col TYPE lvc_t_scol,
      END OF gs_mat,
      gt_mat LIKE TABLE OF gs_mat.
DATA gs_col LIKE LINE OF gs_mat-it_col.

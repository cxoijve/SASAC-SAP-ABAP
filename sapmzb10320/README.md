## Screen Basic 정리 2

###  310 프로그램에서 기능 추가 구현 (정리 표)
| 구분                | **SAPMZB10310**     | **SAPMZB10320**                           |
| ----------------- | ------------------- | ----------------------------------------- |
| **검색 조건**         | Airline, Flight No. | Airline, Flight No., Date                 |
| **기본값**           | KA / 0017 고정        | KA / 0017의 **최신 일자** (SORT + READ TABLE)  |
| **출력 정보**         | 항공사명, 출발/도착 공항명     | 항공사명, 운임(Airfare), 통화(Currency)           |
| **추가 버튼**         | 없음                  | **Conn Info** 버튼 → Screen 200 이동          |
| **Screen 200 내용** | 항공사명, 출발/도착 공항명     | 항공사명, 출발/도착 공항명 (310과 유사하지만 연결 정보 중심)     |
| **버튼 활성화 제어**     | 없음                  | 검색 성공 시만 Conn Info 버튼 활성화 (SCREEN-ACTIVE) |


  
### 출력 결과 정리
- https://zest-kitchen-ec0.notion.site/SAPMZB10320-24a7be15f9c8808e91fbfe9fd45b4bb5?source=copy_link

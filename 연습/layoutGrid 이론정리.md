# grid

grid는 두가지만 이해하면 된다.

1. 컨테이너 속성으로 격자를 만들고
2. 아이템 속성으로 격자에 끼워 넣는다.

## [ container, item ]

**[container]**

- **display**

  값 : flex, grid, block, inline

- **grid-template** : 행의개수 / 열의개수
- **grid-template-rows|columns** : 명시적 행|열의 개수

  값 : 1fr(비율), 200px, repeat(3, 1fr)

**[items]**

- **grid-area** : container의 grid-template-areas 와 연계해서 씀(이름 붙여주기)

- **grid-area**: (r-start,c-start,r-end,c-end)

  - **grid-row|column** : 위치 지정 및 길이 늘려줌
    - grid-row|column-start
    - grid-row|column-end

- **order**(default:0) : 자동배치 되는 순서 변경(음수 사용 가능)

- **z-index**(default:0): 다른 item과 겹칠때 누가 우선일지 지정

### 단위

열(column)을 pixel, percentage, 혹은 ems로 설정시, `fr`로 설정된 것들은 다른 열을 쓰고 남은 공간으로 나뉘어집니다.

ex) grid-template-columns : 1fr 2fr 100px 25%

​ 3번째를 100px쓰고, 4번째를 전체의 25%를 쓰고 남은 부분의 1/3, 2/3이 각각 첫번째,두번째에 부여된다.

---

### 유용한 함수, 변수

- repeat : 1개만 반복이 아니라 (2, 1fr 2fr) 이렇게 여러개 반복도 가능

- span : 확장(item)

  start에 있을때랑 end에 있을때랑 다르다.

  ex) span 3 / 4; : 4를 기준으로 -3만큼 확장 (=1/4), 1/span 3; : 1을 기준으로 +3만큼 확장(=1/4)

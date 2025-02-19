# SnakeGame
c++ project

## **Game Rules**

### Rule 1: Snake Movement
- Snake는 방향키로 조정하며, 같은 방향의 방향키 입력은 무시한다.
- Snake는 진행 방향의 반대 방향으로는 움직일 수 없다.
- Snake는 자신의 Body를 통과할 수 없다.
- Snake는 Wall을 통과할 수 없다.
- Snake는 일정 시간(Tick)에 따라 이동한다.

### Rule 2: Items
- Snake의 이동 방향에 아이템이 있으면 획득한다.
  - **Growth Item**: Body의 길이가 1 증가한다.
  - **Poison Item**: Body의 길이가 1 감소한다.
- Body의 길이가 3보다 작아지면 게임에 실패한다.
- 아이템은 일정 시간이 지나면 다른 랜덤 위치로 이동한다.

### Rule 3: Gate
- Gate는 두 개가 한쌍으로 나타나며 겹치지 않는다.
- Gate는 벽에 위치하고, Snake가 진입하면 다른 Gate로 진출한다.
- Gate는 한 번에 한 쌍만 나타난다.
- Gate는 Snake가 진입 중에는 사라지지 않으며 다른 위치로 이동하지 않는다.

### Rule 4: Gate Behavior
- Gate가 나타나는 벽이 가장자리에 있으면:
  - **상단 벽**: 아래 방향으로 진행한다.
  - **하단 벽**: 위 방향으로 진행한다.
  - **좌측 벽**: 오른쪽 방향으로 진행한다.
  - **우측 벽**: 왼쪽 방향으로 진행한다.
- Gate가 Map의 가운데 벽에 있으면:
  1. 진입 방향과 일치하는 방향으로 진출한다.
  2. 진입 방향의 시계 방향으로 진출한다.
  3. 진입 방향의 반시계 방향으로 진출한다.

### Rule 5: Wall
- Wall은 Gate로 변할 수 있다.
- Immuned Wall은 Gate로 변할 수 없다.
- 모든 Wall은 Snake Head와 부딪히면 실패한다.

### Rule 6: Scoring
- **게임 중 최대 길이**: (현재 길이) / (최대 길이)
- **Growth Item 획득**: (획득한 Growth Item의 수)
- **Poison Item 획득**: (획득한 Poison Item의 수)
- **Gate 통과**: (통과한 Gate의 수)
- **게임 시간**: (시간, 초 단위)

### Game Mission
- 주어진 미션을 달성해야 한다:
  - 미션: 주어진 양 이상으로 길이, Growth Item, Poison Item, Gate를 획득하고 통과한다.

### Custom Rules
- 각 스테이지에는 길이 4-10인 Map 가운데 벽이 2-4개 랜덤으로 생성된다.
- 각 스테이지의 Tick은 50-300ms이다.
- **Time Item**을 획득하면 Tick이 일정 시간 동안 1.5배로 증가한다.

## **실행 화면**

![image](https://github.com/user-attachments/assets/b8ad9471-79aa-4dc6-89ad-7b6047f5d982)

1. 'p'를 누르면 게임이 실행된다.
   
![image](https://github.com/user-attachments/assets/81a167a9-f483-4fb6-b3c2-3a1c124d8d19)
2. map은 랜덤으로 지정되며, map 우측에는 ScoreBoard와 MissionBoard가 뜬다.

![image](https://github.com/user-attachments/assets/9524df9f-0ea1-4dd5-b5d6-47c0373ef69a)
3. 미션 성공시, 다음 stage로 넘어갈 수 있다.
4. 'E'를 누르면 게임이 종료된다.

## **설치 방법**

프로젝트의 결과물을 사용하기 위한 방법은 다음과 같습니다:
1. ncurses 를 설치한다.
   
    sudo apt-get update
  
    sudo apt-get install libncurses5-dev libncursesw5-dev
  
2. 코드를 다운 받는다.
3. 다운된 폴더로 이동하기
4. 실행파일 만들기
     cd SnakeGame
5. 실행파일 만들기
   
    cmake CMakeLists.txt
   
    make
6. 실행하기
    ./snakegame

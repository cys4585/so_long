# subject requirements

# So Long

## 1. Foreword (서문)

개발자가 되는 것은 너만의 게임을 만드는 훌륭한 일이다. 그러나 좋은 게임은 좋은 자산이 필요하다. 2D 게임의 경우 타일, 타일 세트, 스프라이트 및 스프라이트 시트를 검색해야 한다. 고맙게도 일부 재능 있는 예술가들은 [itch.io](http://itch.io)과 같은 플랫폼에서 자신들의 작품을 기꺼이 공유한다. 니가 무엇을 하든 다른 사람의 일을 존중하려고 노력해라.

---

## 2. Goals (목표)

이 프로젝트의 목표는 엄격함(Rigor), C의 사용, 기본 알고리즘의 사용, 정보 조사 등 이번 첫 해의 모든 목표와 유사하다.

그래픽 디자인 프로젝트인 **so long**은 windows, colors, events, textures 등과 같은 스킬을 향상시킬 수 있게 해줍니다.

---

## 3. Common Instructions (공통 지침)

- 당신의 프로젝트는 Norm에 따라 작성되어야 한다. 보너스 파일/함수가 있는 경우 Norm 검사에 포함되며, 내부에 norm error가 있을 경우 0점을 받는다.
- functions는 정의되지 않은 동작(undefined behaviors) 외에 예기치않게 종료되지 않아야 한다(segmentation fault, bus error, double free, etc). 이 경우, 프로젝트는 작동하지 않는 것으로 간주되어 평가 중에 0을 받게된다.
- Heap에 할당된 메모리 공간은 필요할 때 적절하게 해제되어야 한다. leak은 허용되지 않는다.
- subject가 요구하는 경우, `-Wall`, `-Wextra` 및 `-Werror` 플래그를 사용하여 소스 파일을 필요한 출력(output)으로 컴파일할 **Makefile**을 제출해야 하며, Makefile은 relink되지 않아야 한다.
- **Makefile**은 적어도 `$(NAME)`, `all`, `clean`, `fclean` 및 `re`는 포함해야 한다.
- 프로젝트에 보너스를 제출하려면, Makefile에 `bonus` 규칙을 포함해야 한다. `bonus` 규칙은 프로젝트의 main part에서 금지된 모든 헤더, 라이브러리 또는 함수를 추가한다. 보너스들은 `_bonus.{c/h}` 파일에 있어야 한다. Mandatory 및 bonus 파트 평가는 별도로 수행된다.
- 프로젝트가 너의 libft를 사용하는 것을 허락한다면, libft 폴더에 소스들과 관련 Makefile을 카피해야 한다. 프로젝트의 Makefile은 libft의 Makefile을 사용해 라이브러리를 컴파일한 뒤, 프로젝트를 컴파일 해야한다.
- 이 작업이 제출되지 않아도 되고 등급이 지정되지 않더라도 프로젝트를 위한 테스트 프로그램을 만들 것을 권장한다. 그것은 너와 평가자의 일을 쉽게 시험할 기회를 줄 것이다. 그 테스트들은 방어하는 동안 특히 유용하다는 것을 알게될 것이다. 실제로 디펜스 동안에, 너의 테스트나 평가자의 테스트를 자유롭게 사용할 수 있다.
- 할당된 git repository에 작업을 제출한다. git repository에 있는 작업만이 평가될 것이다. 만약Deepthought가 당신의 작업을 평가하도록 지정되면, 그것은 당신의 동료 평가 후에 이루어질 것이다. 만약 Deepthought의 평가 중 작업의 일부에서 에러가 발생한 경우, 평가는 중지된다.

---

## 4. Mandatory part - so long

| Program name | so_long |
| --- | --- |
| Turn in files | All your files |
| Makefile | all, clean, fclean, re, bonus |
| Arguments | a map in format *.ber |
| External functions | - open, close, read, write, printf, malloc, free, perror, strerror, exit
- All functions of the MinilibX |
| Libft authorized | Yes |
| Description | 돌고래가 물고기 몇 마리를 잡아먹은 뒤 지구를 탈출하는 작은 2D 게임을 만들어야 한다. 또는, 영웅이 특정 수집품을 모은 뒤 공간을 떠나는 방식이면 된다. |

제약조건은 다음과 같다:

- **MiniLibX**를 사용해야만 한다. 운영체제에서 사용할 수 있는 버전 또는 제공되는 소스 중 하나를 사용해야 한다. 만약 제공받은 소스로 작업하기로 했다면, libft의 공통 지침과 같은 규칙을 따라야 한다.
- window 관리는 원활하게 유지되어야 한다: 다른 window로 바꾸기, 최소화 등.
- 돌고래 테마와 함께 예시가 주어지지만, 원하는 무엇이든 사용할 수 있다.
- 맵은 벽(walls), 수집품(collectibles), 자유 공간(free space) 3가지 요소로 구성될 것이다.
- 플레이어의 목표는 최소한의 움직임(movement)으로 지도에 있는 모든 수집품을 수집하고, 탈출하는 것이다.
- 모든 이동에서 현재 이동 횟수가 shell에 표시되어야 한다.
- 플레이어는 상하좌우로 움직일 수 있어야만 한다.
- 2D 시점을 사용할 것이다 (top-down or profile).
- 게임이 실시간(real-time)일 필요는 없다.
- 플레이어는 벽으로 움직일 수 없다.
- 프로그램은 윈도우에 이미지를 표시하고, 다음 룰을 준수한다:
    - W, A, S, D 키는 주인공을 이동시키기 위해 사용될 것이다.
    - ESC를 누르면 윈도우를 닫고 프로그램이 깔끔하게 종료돼야 한다.
    - 윈도우 창에 있는 red cross를 클릭하면 윈도우를 닫고 프로그램이 깔끔하게 종료돼야 한다.
    - miniLibX의 image를 사용하는 것이 강력히 추천된다.
- 프로그램은 첫번째 인자로 `.ber` 확장자를 가진 맵 기술(map description) 파일을 취해야 한다.
    - 맵은 5개의 문자로만 구성돼야 한다.
        - 0: 빈 공간 (empty space)
        - 1: 벽 (wall)
        - C: 수집품 (collectible)
        - E: 맵 탈출 (map exit)
        - P: 시작 위치 (player’s starting position)
        - 간단한 유효한 맵:
            
            ```
            1111111111111
            10010000000C1
            1000011111001
            1P0011E000001
            1111111111111
            ```
            
    - 맵은 벽(1)으로 둘러싸여야 하며, 그렇지 않으면 프로그램은 에러를 리턴해야 한다.
    - 맵은 적어도 한개의 탈출(E), 수집품(C), 시작 위치(P)를 가져야 한다.
    - 지도에 유효한 경로가 있는지 체크할 필요는 없다.
    - 맵은 직사각형이어야 한다.
    - 맵의 규칙을 준수하는 한 어떤 종류의 맵이라도 파싱(분석)할 수 있어야 한다.
    - 또다른 최소한의 `.ber` 지도:
        
        ```
        1111111111111111111111111111111111
        1E0000000000000C00000C000000000001
        1010010100100000101001000000010101
        1010010010101010001001000000010101
        1P0000000C00C0000000000000000000C1
        1111111111111111111111111111111111
        ```
        
    - 파일에 어떤 잘못된 구성이 있을 경우, 프로그램은 적절히 exit 해야하고, “Error\n” 뒤에 선택한 명시적 에러 메시지를 return 해야한다.

---

## 5. Bonus part

(Warning) 보너스는 만다토리 파트가 퍼펙트한 경우에만 평가될 것이다. 퍼펙트하다는 것은 당연히 완전해야 한다는 것을 의미하며, 잘못된 사용 등과 같은 심각한 실수가 있더라도 실패할 수 없다는 것을 의미한다. 채점 과정에서 만다토리 파트가 모든 점수를 획득하지 못하면 보너스는 완전히 무시된다는 의미다.

평가 중에 정당하게 사용한 한 보너스 파트를 완성하기 위해 다른 함수를 사용할 수 있다.

보너스 목록:

- 적의 순찰은 플레이어가 접촉할 경우 패배하게 한다.
- 스프라이트 애니메이션이 있다.
- 움직임 카운트가 shell output 대신에, 스크린에 직접적으로 표시된다.

(Insight) 나중에 더 나은 게임을 만들 수 있을 것이다. 너무 많은 시간을 낭비하지 마!

---

## 6. Examples

![그림1: 매우 나쁜 그래픽 디자인 취향을 가진 예시](./assets/Untitled.png)

그림1: 매우 나쁜 그래픽 디자인 취향을 가진 예시

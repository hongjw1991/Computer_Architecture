### 카르노맵
- 일반 불대수식을 최소항 전개로
  - a'c + b'c' + ab : 이 각각은 최소항이 아니다. 
    - a'c(b+b') + b'c'(a+a') + ab(c+c') = a'cb + a'cb' + b'c'a +b'c'a' + abc + abc' 으로 하면 각각이 최소항이 된다. 즉, 최소항 전개가 되었다.
  - ![Alt text](/images/logic_circuit/4-0.png)
    - 이와 같이 최소항 최대항을 표시할수도 있다. 즉, 최소항의 부정은 최대항이 되는 것.
- 카르노맵
  - 간략화
    - 이전에 배운 간략화는 체계적이지 않다.
    - 최소식 보장이 되지 않는다.
    - 그래서 위 두 가지 문제를 해결하기 위해 제시된 것이 카르노맵
  - 카르노맵이란?
    - 그림은 다음을 참조
      - 참조
    - 최소 논리곱의 합
      - 최소 개수의 항
      - 각 항은 최소개수의 문자로 구성
    - 위의 최소 논리곱의 합을 그림으로 표현하여 간략화의 목적에 부합하도록 제시된 것을 의미한다.
    - 2변수 카르노맵
      - 사실 2변수일 때는 명확하기 때문에 거의 쓰이지 않는다.
    - 3변수 카르노맵
      - 위의 참조링크를 들어가서 확인
    - 4변수 카르노맵
      - 참조링크 확인
- 무관항이 포함된 함수
  - 불완전명세함수
    - 무관항을 통해 카르노맵에서 최소항을 묶을 때, 더 크게 묶어서 간략화할 수 있다.
- 최소 논리합의 곱
  - ![Alt text](/images/logic_circuit/4-1.png)
    - 위와 같이 한다. 1만 고를 때와 달리 0만 찾아서 묶어서 한다.
- 항에 대해
  - 관련항(implicant) 또는 항
    - 한 개 이상의 1의 묶음
  - 주항(prime implicant)
    - 더 이상 다른 항과 결합될 수 없는 항
    - 최소 논리곱의 합은 주항들로 이루어진다.(지금까지의 간략화로 했던 것은 모두 주항)
    - 어떤 주항은 최소 논리곱의 합에 포함되지 않는다.(문제점)
      - ![Alt text](/images/logic_circuit/4-2.png)
      - 이와 같이 총 6개의 주항을 가지는 카르노 맵에서 최소식은 a'b'd+bc'+ac이다. 즉, 어느 주항을 선택할 것인가가 중요하다.
  - 필수 주항(essential prime implicant)
    - 한 최소항이 단 하나의 주항에만 포함되면 그 주항을 필수 주항이라 부른다.
    - 필수 주항은 반드시 최소 논리곱의 합에 포함된다.
      - ![Alt text](/images/logic_circuit/4-3.png)
      - 여기서 b'c는 필수 주항이므로 반드시 식에 포함된다. v표시가 된 1은 이것이 아니면 가장 간략화된 방식으로 표현될 수 없다.
      - 이외에 bd(중간에 4개)도 필수 주항, 그 아래에 1은 우측 4개를 통해 ac로 포함되어 필수 주항이 된다. 따라서
      - 식 f = b'c + bd + ac
      - 이와 같이 필수 주항을 찾아서 카르노맵을 이용해야 한다.
    - 이 때, 필수 주항을 모두 커버하고 나면 남는 1이 있을 것이다. 물론 이 중에서도 최소식을 찾는 방법이 있으나 복잡함. 이 때는 최소식이 여러 개 포함될 수 있다.
    - 필수 주항 판별
      - 주어진 최소항과 인접한 1이 모두 하나의 항에 포함되면 그 항은 필수 주항
      - 즉, 특정 최소항을 기준으로 인접한 1을 모두 커버 가능한지 확인하여 불가하면 그것으로 판별되지 않는 것이며, 가능하면 필수 주항을 만들 수 있는 것이다.
      - 물론 인접한 경우를 찾을 때는 무관항도 포함한다.

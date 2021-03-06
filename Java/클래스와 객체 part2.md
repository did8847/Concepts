# 클래스와 객체

## #1 method & return

- method

  - 작업(기능)을 수행하기 위한 명령문들의 집합이라고 보면 된다.
  - 메서드는 선언부와 구현부로 나뉜다.
    - 선언부 : 호출할 때 필요
    ```java
    ex) int add(int x, int y) { } -> 중괄호 안이 구현부
    ```

- return

  - 개념

    - 매개변수(인자값,arguments,parameter)로 값을 받아서 그 결과를 리턴값(반환값)으로 돌려준다.
      - 단, 매개변수가 없을 수 있으며, 리턴타입이 'void'라면 결과를 돌려주지 않아도 문제없다.
    - 현재 실행중인 메서드를 중지한 후 호출한 곳으로 이동

      ```java
      // return 값 존재 시
      return; // return문만 작성

      // return 값 미존재 시
      return YM; // return + 리턴값
      ```

  - 특징
    - 반복적으로 수행된다고 판단되는 여러 문장이 있다면, 메서드로 작성하는 편이 좋다.
    - 코드 관리가 용이하다.
    - 한가지 메서드는 한가지 기능만 수행하는 편이 좋다.
    - <span style="color:red">**코트 중복 제거, 누가 봐도 알아볼 수 있는 프로그램이 되도록 노력, 재사용성 향상(프로그래머의 기본 자질)**</span>

---

## #2 Call Stack & 매개변수

- JVM의 메모리 구조

  - 메서드 영역, Class영역, Static영역

    - Class 정보와 Class 변수가 저장되는 곳
    - Static이 붙은 변수나 메서드가 저장되는 곳

  - 호출스택 (Call Stack)

    - <span style="color:red">후입선출 개념</span>
    - 메서드의 작업 공간
    - 메서드가 호출되면 메서드 수행에 필요한 메모리 공간을 할당받고 메서드가 종료되면 사용하던 메모리를 반환한다.
    - <span style="color:red">생성자 및 메서드 호출 시에 필요한 메모리 공간을 스택 공간에 할당한다.</span>
    - <span style="color:red">**호출 스택에서 맨 위에 있는 메서드가 현재 실행 중이며, 아래에 있는 메서드가
      바로 위에 메서드를 호출하고 대기상태로 있다.**</span>

  - 힙(Heap)
    - 인스턴스가 생성되는 공간
    - new연산자에 의해서 생성되는 배열과 객체는 모두 여기에 생성된다.

- 기본형 매개변수 & 참조형 매개변수

  - 기본형 매개변수 : <span style="color:red">read only</span>

    - 흔히, C언어에서 <span style="color:#3300CC">call by value</span>로 불린다.
    - <span style="color:green">메서드 호출 시에 매개변수로 넘겨주는 값은 메서드의 지역변수로 복사가 이루어지는 형태</span> (수정을 해도 호출한 메서드 값에는 전혀 영향을 미치지 않는다.)

  - 참조형 매개변수 : <span style="color:red">read & write</span>
    - 흔히, C언어에서 <span style="color:#3300CC">call by reference</span>로 불린다.
    - <span style="color:green">메서드 호출 시에 매개변수로 넘겨주는 값은 주소값을 넘겨주는 형태</span> (수정을 할 시, 호출한 메서드의 값에도 직접적으로 영향을 미친다.)

---

## #3 재귀 호출(recursive call)

- 재귀 호출 ex) 팩토리얼, 제곱, 트리, 폴더목록 등
  - <span style="color:red">메서드 내에서 자기자신을 반복적으로 호출하는 것을 말한다.<span/>
  - 재귀 호출은 얼마든지 반복문으로 바꿀 수 있다.
  - 또한, 반복문보다 성능이 떨어진다.(스택에 계속 쌓인다.)
  - 그래도, 코드가 간결하고 가독성이 좋아 많이 사용한다.

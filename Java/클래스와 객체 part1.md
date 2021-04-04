# 클래스와 객체

## #1 객체지향언어

- 객체(object)란?

  - 세상에 존재하는 모든것을 의미한다. 죽, 주변에 있는 사물이나 생명체와 같은 모든것들을 말한다.
  - 프로그래밍에서의 객체는 데이터의 분산을 막기 위해 데이터와 기능을 하나로 묶은 그룹이라고 볼 수 있다.
    - ex) 컴퓨터(PC) = 데이터(본체, 모니터 등) + 기능(화면제공, 소리 등)

- 객체지향언어(Object-oriented Language)란?

  - 컴퓨터 프로그래밍의 한가지 기법으로, 프로그램을 그저 데이터와 처리방법으로 나누는게 아니라 프로그램에 다수의 <span style="color:red">**객체**</span>를 만들고 이들이 서로 상호작용을 통해 만들어지는 방식이다.
    - ex) 컴퓨터(<span style="color:red">**프로그램**</span>)의 기능이 제대로 작동하기 위해서는 RAM,CPU,SSD 등의 컴퓨터 부품 및 주변기기(<span style="color:red">**객체**</span>)가 필요하다.

- 객체지향언어의 특성

  - <span style="color:red">코드의 재사용성이 매우높다.</span>
    - 새로운 코드를 작성할 때, 이미 만들어 놓은 코드를 이용해서 쉽게 작성이 가능하다.(상속,클래스 등등)
  - 코드의 관리가 쉽다.
    - 코드간의 직,간접적인 관계를 맺어줌으로써 보다 적은 노력으로 코드 변경이 가능하다.
  - 보안과 신뢰성이 높은 프로그램 개발을 가능하게 한다.
    - 제어자(접근제어자)와 메서드를 이용하여, 데이터의 <span style="color:blue">**캡슐화**</span>가 가능하고, 코드의 중복을 제거하여 코드의 불일치로 인한 예외를 방지할 수 있다.
      - <span style="color:blue">**캡슐화**</span>:데이터와 코드의 형태를 외부로부터 알 수없게 하고, 데이터의 구조와 역할, 기능을 하나의 캡슐형태로 만드는 방법이다.
  - 기존의 절차지향적 언어와 별반 다르지 않다. 약간의 규칙만 추가되었다.

## #2 클래스와 인스턴스의 개념과 활용

- 클래스와 객체의 관계

  - 클래스란 객체를 정의해놓은 코드이며, 객체를 생성하는데 사용된다.
  - ex)
    | <span style = "color:green">클래스</span> | <span style = "color:green">객체(인스턴스)</span> |
    |:----------:|:-------------:|
    | 상품 설계도 | 상품 |
    | 모니터 설계도| Monitor |
    | 붕어빵 기계 | 붕어빵 |
  - <span style = "color:red">객체는 클래스에서 정의된 내용대로 메모리에 생성된 것을 의미한다</span>

- 객체의 구성요소

  - 객체는 통상 <span style = "color:red">속성(멤버 변수)</span>와 <span style = "color:red">기능(멤버 메서드)</span>로 되어 있다.
    - 물론, 속성과 기능 없이도 객체를 만들 수 있으나 의미가 없다.

  ```java
      public class Monitor{

          // 속성(변수)   ex) 색상,채널,전원 등
          String color;             // 모니터의 색
          int channel;              // 채널
          boolean power;            // 전원

          // 기능(메서드) ex) 볼륨 조절,채널 변경 등
          public void power() {
              this.power = !power;  // 전원 on,off 기능
          }
          public void channelUp() {
              this.channel++;       // 채널 높이기
          }
          public void channelDown {
              this.channel--;       // 채널 낮추기
          }
      }
  ```

- 인스턴스 생성 코드

  - 클래스명 참조변수;<br/>참조변수명 = new 클래스명();

  ```java
  ex) // monitor참조변수의 타입이 Monitor이다. null로 초기화
     Monitor monitor = null;
     // new연산자로 Monitor의 인스턴스를 만들어 heap에 할당
     monitor = new Monitor();
     // 참조변수(리모컨)으로 인스턴스를 조작
     monitor.power();
  ```

  - <span style = "color:red">**monitor라는 참조변수는 Monitor를 조작하는 리모컨과 같은 개념**</span>

- 인스턴스의 사용
  - <span style = "color:red">여러 개의 참조변수가 하나의 인스턴스를 가리키는 경우는 얼마든지 가능하다. 하지만 하나의 참조변수가 여러개의 인스턴스를 가리키는 것은 불가능하다.</span> -> 하나의 변수에는 하나의 값만 들어가기 때문에

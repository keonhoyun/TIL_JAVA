# :coffee: TIL_Java(Class~다형성)

## Class 구성과  Ojbect 사용법

- 클래스의 구조

```java
public class Member{ // 클래스 선언
    String name; // 데이터를 저장하기 위한 변수선언
    int age; 
    String email;
    public void memberlnfo90{ // 필요한 기능 정의
        String info = name
    }
}
```

### 생성자

> 생성자는 객체 생성시 자동 호출되는 특별한 기능으로 주로 객체 초기화 작업을 수행한다. 클래스와 이름이 같고 , 리턴 타입이 반드시 없어야 하며 객체 생성시에 항상 호출되어지기 때문에 반드시 있어야한다.

```java
class Member{
    String name;
    int age;
    String email;
    
    public Member(String name, int age, String email){
        this.name = name;
        this.age = age;
        this.email = email;
    }
    
}
```

> 생성자를 정의시에는 기본 생성자도 같이 정의를 해주는 것이 바람직

#### This variable

> 객체 생성시 그 객체의 레퍼런스를 저장하기 위한 this 레퍼런스가 자동 생성된다. 메서드(생성자) 수행 시에 현재 수행중인 객체의 레퍼런스 정보를 가지고 있는 this를 사용할 수 있다.

> 현재 실행중인 객체의 위치 variable
>
> 현재 실행중인 객채의 위치값: this
>
> 현재 실행중인 객체의 맴버변수: this.변수명
>
> 현재 실행중인 객체의 메서드: this.메서드명
>
> 현재 실행중인 객체의 생성자: this(args list)
>
> 반드시 생성자의 첫라인에서만 사용

### Method

> 클래스내에 객체가 가져야할 기능 정의시에 메서드를 사용한다.

> 메서드는 객체가 가져야할 기능을 구현한다.
>
> 기능 수행시 필요한 정보를  parameter list를 이용하여 입력받는다.
>
> 결과값을 필요에 따라 method를 호출한 측에 return을 이용하여 결과값을 전달한다.
>
> 전달할 결과값이 없을 경우 return_type을 void라 명시한다.
>
> Overloading 기법을 이용하여 같은 이름의 method를 정의할 수 있다.

#### member variable

> class내에 정의되는 변수
>
> 메모리 영역 중 heap에 생성된다.
>
> static 변수: class가 메모리에 로딩시에 메모리 할당이 이루어짐, 자동초기화
>
> 인스턴스 변수: 객체 생성시 자동 초기화, 객체 제거시 제거

#### Method Overloading

같거나 비슷한 일을 하는 메서드 구현 시에 메서드의 이름을 같게 정의하여 사용을 편리하게 한다.

```java
class OverloadTest{
    public String print(String x, String y){
        // 실행문
    }
    public String print(String x, int y){
        // 실행문
    }
    public String print(int x, int y){
        // 실행문
    }
}
```



### 접근제한자

> 클래스 정의시 접근 단계를 정의하기 위하여 접근제한자를 이용한다.

| 종류      | 같은 클래스 | 같은 패키지 | 다른 클래스 | 전체 |
| --------- | ----------- | ----------- | ----------- | ---- |
| private   | O           |             |             |      |
| (default) | O           | O           |             |      |
| protected | O           | O           | O           |      |
| public    | O           | O           | O           | O    |

- private: 같은 클래스 내에서만 사용
- default: 같은 클래스, 같은 패키지 내에서만 사용
- 패키지가 다른 사용 X, 상속받으면 사용
- public  어디서나 사용

#### 사용제한자

- static: 객체 생성없이 사용하고자 할 때
- final: 변경불가
- abstract: 미완성



### API

> 객체지향에서  class 단위로 미리 구현되어 제공되는 프로그램



## 상속

### 상속

> class 설계시 특정 class를 상속받아 그 class의 변수와 기능을 사용할 수 있도록 한다.
>
> extends를 이용하여 상속받음
>
> ```java
> public class MainMember enxtends Memter{
>     // 내용
> }
> ```
>
> 

#### Generalization

- 추출된 class의 공통적인 특성을 모아 super class로 정의할 수 있다.

#### Specializtion

- 비슷한 속성과 기능을 가지고 있는 다른 class를 상속받아 새로운 class를 정의

#### super keyword

> 현재 수행중인 객체가 상속받은 상위 객체의 레퍼런스를 갖는 reference variable로 객체 생성시 자동으로 생성

- super
  - 현재 수행중인 객체의 상위 객체의 reference를 가짐
- super.memberVariable
  - 현재 수행중인 객체의 member variable과 상속받은 super 객체의  member variable 이름이 같은 경우 사용
-  super.method()
  - 상속받은 메서드 호출시, 현재 수행중인 객체와 상속받은 객체의 매서드명이 같을 경우 사용



### 메서드 오버라이딩

> 상속받은 super의 method 중 특정 method의 내용을 수정, 추가하여 정의하는 기법

#### 규칙

> sub 클래스의 오버라이딩되는 메서드는 상속받은 super 클래스와 아래 내용이 반드시 같아야한다.
>
> - Name
> - Return type
> - Argument list
> - Acess modifier는 같거나 넓은 범위

### 오버로딩 VS 오버라이딩

#### 공통점

- 메서드 정의시 사용
- 메서드와 이름을 같게 정의
- 사용의 편리성
- 다형성 효과

#### 오버라이딩

- 상속을 기반
- super로 부터 상속받은 기능 중 특정 기능을 재정의

#### 오버로딩

- 메서드 이름은 같게 매개변수는 다르게
- 나머지 메서드 형식은 상관X



### 다형성

> object 다형성과 method 다형성으로 구분 

#### Object polymorphism

> 같은 타입의 변수가 다양한 형태의 객체를 참조하는 것
>
> sub 객체 생성시 super도 같이 생성, super type으로 변수 선언 가능

#### method polymorphism

> 같은 클래스 타입의 같은 메서드를 호출 시 그 기능이 다양하게 처리되는 것

> 메서드 호출 시 VM은 그 메서드가 Overriding되어 있는지 여부 확인, 생성된 객체의 상속 관계에서 마지막 오버라이딩된 메서드 호출

###
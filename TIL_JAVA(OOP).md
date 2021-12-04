# TIL_JAVA(OOP)

## OOP

### 객체지향 프로그래밍

> 객체(주체가 아닌 것, 주체가 활용하는 것)
>
> 주변의 많은 것들을 객체화 해서 프로그래밍하는 것
>
> 객체가 갖는 속성과 기능은 추상화되어 클래스에 정의된다.
>
> 클래스는 구체화되어 프로그램의 객체가 된다.



#### 장점

> 블록 형태의 모듈화된 프로그래밍
>
> 신뢰성이 높다.
>
> 추가/수정/삭제가 용이
>
> 재사용성 高



#### 클래스

> 객체를 정의해 놓은 것, 객체의 설계도(틀)
>
> 클래스는 직접 사용 不可



#### 객체

> 클래스를 테이터 타입으로 메모리에 생성된 것
>
> 클래스를 구체화, 객체화시키면 된다.



```java
// 추상화로 클래스 만들기
public class Person{
    String name;
    int age;
    boorlean isHungry;
    
    void eat(){
        System.out.println("냠냠");
        isHungry = false;
    }
    void work(){
        System.out.println("열심히");
        isHungry = true;
    }
}
```



```java
// Person을 객체화 해서 사용
public class PersonTest{
    public static void main(String[] args){
        Person person1 = new Person();
        ````````
    }
}
```



#### 객체 생성과 메모리

##### class area

> 클래스 원형 로딩
>
> - 필드 정보
>
> - 메서드 정보
>
> - 타입 정보
>
> - 상수 풀



##### method stack

> 매서드들의 실행공간
>
> - thread별로 별도 관리
> - 메서드 호출 순서대로 쌓이는 구조
> - 메서드 프레임에 로컬변수도 쌓이는 구조
> - 로컬변수는 선언된 영역을 벗어나면 삭제



##### heap

> 객체를 저장하기 위한 영역
>
> - thread에 의해 공유
> - 생성된 객체를 프로그래머가 삭제 不可



```java
public static void main(String[] args){
    Person person1 = new Person();
    person1.name = "홍길동";
    person1.isHungry = true;
    person1.eat();
}
// 클래스 영역 : Person -> name, age, isHungry, eat(), work(), PersonTest -> main()

// 스택 영역: Person person1

// 힙 영역: name, age, isHungry, 홍길동
```



### 변수의 종류

#### 타입에 따라

| 변수 종류               | 특징                | 비고                       |
| ----------------------- | ------------------- | -------------------------- |
| Primitive Type variable | 기본 8가지 type변수 | int i, char c, float f     |
| Reference Type variable | 나머지 모든 것      | String s, int[] points.... |

#### 선언 위치에 따라

| 종류      | 변수종류           | 선언 위치   |
| --------- | ------------------ | ----------- |
| 맴버 변수 | 클래스 멤버변수    | 클래스 영역 |
| 맴버 변수 | 인스턴스 멤버 변수 | 클래스 영역 |
| 지역 변수 | 지역 변수          | 함수 내부   |
| 지역 변수 | 파라미터 변수      | 함수 선언부 |

```java
int instanceVariable; // 인스턴스 맴버 변수
static int classVariable; // 클래스 멤버 변수
```

```java
public static void main(String[] args){ // 파라미터 변수
    int localVariable = 10; // 로컬 변수
}
```



#### 인스턴스 변수

> 클래스 영역에 선언
>
> 변수의 생성 - 객체가 만들어질 때 객체 별로 생성
>
> - 생성 메모리 - heap
>
> 타입 별로 default 초기화
>
> - 객체를 만들 때마다 객체 별로 생성(객체마다 고유값 유지)
> - Garbage Collector에 의해 객체가 없어질 때 소멸



#### 클래스 맴버 변수

> 클래스 영역에 선언, static 키워드 붙임
>
> 변수의 생성 - 클래스 로딩시 메모리 등록
>
> - 개별 객체의 생성과 무관
> - 모든 객체가 공유
>
> 타입 별로 default 초기화
>
> 객체 생성과 무관하게 클래스 이름으로 접근
>
> 프로그램 종료시 소멸



#### 지역 변수 & 파라미터 변수

> 클래스 영역의 {} 이외의 모든 중괄호 안에 선언
>
> 선언된 라인이 실행될 때 생성
>
> 사용 전 명시적 초기화 必
>
> 외부에서 접근 不可
>
> 선언된 영역을 벗어날 때 소멸



### 메서드

> 현실의 객체가 하는 동작을 프로그래밍 화
>
> 작업을 수행하는 명령문의 집합
>
> 반복 사용되는 코드의 중복 방지
>
> 반환값이 없을 경우 void

#### 오버로딩

> 동일한 기능을 수행하는 메서드의 추가작성
>
> 기억해야할 메서드가 감소, 중복 코드를 효과적으로 관리
>
> 매서드 이름은 동일해야함, 파라미터의 순서 or 개수, 타입이 달라야함
>
> - 같으면 오류



### 생성자

> 객체를 생성할 때 호출
>
> new 키워드와 함께 호출
>
> - Person person1 = new Person();
>
> 일반 맴버 변수의 초기화나 객체 생성 시 실행되어야 하는 작업
>
> 메서드와 작성 규칙이 비슷하나 리턴 타입 X, 이름은 클래스와 동일



#### 기본생성자

> 파라미터가 없고 구현부가 비어있음
>
> 생성자 코드가 없으면 컴파일러가 자동 생성

```java
public class DefaultPerson{
    String name;
    int age;
    boolean inHungry;
    // public DefaultPerson() {} -- 생략된 기본 생성자
    
    public static void main(String[] args){
        DefaultPerson person = new DefaultPerson();
    }
}
```



#### 파라미터가 있는 생성자

> 생성자의 목적이 일반 맴버 변수의 초기화 (호출값을 넘겨서 초기화시킴)

```java
public class PrameterPerson{
    String name;
    int age;
    boolean inHungry;
    
    // member변수 초기화
    ParameterPerson(String n){
        name = n;
    }
    
    public static void main(String[] args){
        PrameterPerson person = new PrameterPerson("김태균");
    }
}
```

#### this

> 참조변수로서 객체 자신을 가리킴
>
> 객체에 대한 참조
>
> - static 영역에서 this 사용 不可
>
> 반드시 첫 줄에서만 호출



### 상속

> 기존 클래스의 자산(맴버)을 자식 클래스에서 재사용하기 위한 것



#### super

> super를 통해 조상클래스 맴버 접근
>
> 사용된 위치에서 점점 확장해나가며 처음 만난 선언부에 연결
>
> - method 내부 -> 해당 클래스 맴버 변수 -> 조상 클래스 맴버 변수



### 패키지

> 클래스 파일을 담고 있는 디렉터리
>
> 모든 클래스는 하나의 패키지에 속함
>
> naming 룰
>
> - com.ssafy(회사의 identify).hrm(프로젝트).common(용도).ssafy.......




# Homework

## 1.

```java
1. class Test {
2.         protected static int add(int a, int b) {return a+b;}
3. }

4. class Ex extends Test {
5.        protected static int add(int a, int b) {
6.              int x = super.add(10, 5);
7.              return x;
8.       }
9. }

10. public class Sam {
11.        public static void main(String[] args) {
12.            System.out.println(Ex.add(10, 5));
13.       }
14. }
```



> super는 static에서 쓸 수 없기 때문에 에러이다.
> 또한 파일이름으로 메인메서드를 작성해야한다.
> static메서드는 오버라이딩이 불가



## 2.

```java
class Aclass {
       public int a;
       protected Aclass(int a) { this.a=a; }
}
class Bclass extends Aclass {
       private Bclass(int a) { super(a); }
   
}
public class Cclass
{
  public static void main(String[] args) {
              Bclass ob=new Bclass(420);
              System.out.print(ob.a);
      }
}
```

> 객체 생성 불가
>
> 생성자 메서드를 넣어줘야함



## 3.

```java
class Aclass{}
class Bclass extends Aclass {}
class Cclass extends Aclass {}
    :
Aclass p0= new Aclass();
Bclass p1= new Bclass();
Cclass p2= new Cclass();
Aclass p3= new Bclass();
Aclass p4= new Cclass();
```

> 모두 다 가능!



## 4.

```java
class ClassA {
      public int getValue() {
             int value=0;
             boolean setting = true;
             String title="Hello";
             if (value || (setting && title == "Hello")) { return 1; }
             if (value == 1 & title.equals("Hello")) { return 2; }
     }
}
public class ClassB
{
 public static void main(String args[]){
 ClassA a = new ClassA();
             a.getValue();
 }
}
```

> if (value || (setting && title == "Hello")) { return 1; } 이 부분에서 value가
>
> 논리형 데이터가 아니기 때문에 오류가 발생하였다.



## 5. 

```java
public class ItemTest{
         private final int id;
         public ItemTest(int id){ this.id = id; }
         public void updateId(int newId){ id = newId; }

        public static void main(String[] args){
              ItemTest fa = new ItemTest(42);
              fa.updateId(69);
             System.out.println(fa.id);
      }
}
```

> id에 42가 들어간다. 0은 초기 기본값이기 때문, 
>
> 처음 만들때에 한에서 42가 들어가게된다.



## 6.

```java
class Test {
        public static void go(Long n){System.out.println("Long");}
        public static void go(Short n){System.out.println("Short");}
        public static void go(int n){System.out.println("int");}  
}
public class TestMain
{
        public static void main(String[] args){
             short y = 6;
             long z = 7;
             go(y);
             go(z);
       }
}
```

> Test.go로 바꾼다. 클래스가 없기 때문 -> 접근하지 못한다.



## 7.

```java
public class Test {
      public static void main(String[] args){
           String str = "null";
           if (str == null){
                  System.out.println("null");
           } else if(str.length() == 0) {
                  System.out.println("zero");
          } else {
                  System.out.println("some"); 
         }
     }
}
```

> null값이 아니라 "null"이라는 문자열이 입력되어있다.



## 8. 

```java
class One {
         void foo() { }
 }
 class Two extends One {
        [                ]
 }

 
 [         ] 에 추가 할 수 있는 것을 모두 고르면 ?
 
가. int foo() { /*more code here */ }
나. void foo() { /*more code here */ }
다. public void foo() { /* more code here */ }
라. private void foo() { /*more code here*/ }
마. protected void foo() { /*more code here */ }
사. public  void foo() { /*more code here */ }
```



> 오버라이딩을 시도하고 있다.
>
> void foo()로 선언했기 때문에 void foo로 받아야한다. -> 가 不可
>
> public = 누구나
>
> protected = 같은 패키지, 다른패키지 상속
>
> default = 같은 패키지
>
> private = 같은 클래스



## 9.

```java
35: String #name = "Jane Doe";
36: int $age=24;
37: double _height = 123.5;
38: double ~temp = 37.5;

올바른 것을 모두 고르면 ?

가. 35 라인은 컴파일 되지 않는다.
나. 36 라인은 컴파일 되지 않는다.
다. 37 라인은 컴파일 되지 않는다.
라. 38 라인은 컴파일 되지 않는다.
```

> 변수명: 영, 숫, 특수문자("_", "$") / 단, 숫자는 시작할때 X





## 10.

``` java
[10] 다음 클래스에서 몇 번째 라인을 제거하면 컴파일 오류가 없어지며, 컴파일 오류가 없어진 후 결과는 ?
1:   class Test { }
2:   public class Ex extends Test {
3:       public static void main(String[] args) {
4:            Test t1 = new Test();
5:            Ex e1 = new Ex();
6:            Ex e2 = (Ex)t1;
7:            Object o1 = (Object)t1;
8:            String s1 = (String)t1;
9:            Test t2 = (Test)e1;
10:          System.out.println(t2);
11:     }
12: }
```

> 객체를 하위클래스로 선언시에는 상위클래스로 전환 可 / 그 반대는 X
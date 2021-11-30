# :coffee: TIL_Java(Data Type ~ Array)



## Data Type

### Identifiers

- 클래스내의 식별자(클래스명, 변수명, 상수명, 메서드명 등)을 명명하는 방법
  - 실별자는 class, method, variable 이름을 의미한다.
  - 유니코드문자, $, _, 로 시작 , 두 번째 글자부터 숫자 허용
  - 대소문자 구별, 길이에 제한이 없다.
  - keyword 사용불가
- Class
  - 첫글자 대문자, 나머지 소문자
- method
  - 모두 소문자
- variable
  - 모두 소문자
- constant
  - 모두 대문자
- 합성어는 두번째 단어 첫글자 대문자

```java
// Java Keyword
abstract continue goto package synchronized assert default if private this
boolean do implements protected throw break double import pulic throws
byte else instanceof return transient case extends int short try
catch final interface static void char finally long strictfp volatile
class float native super while const for new switch
```



## 조건문

### if

```java
if(조건){
    // 조건이 참일 경우 실행
}

if(조건){
    // 조건이 참일 경우 실행
}else if(조건2){
    // 조건2가 참일 경우 실행
}else{
    // 나머지
}
```



### switch

```java
switch(expert){ // expert는 반드시 정수형이어야함!!(int, short, byte, char)
    case 값1: // 같은 값을 찾아서 실행
        statements;
        break;
    case 값2:        
        statements;
        break;
    default: // 같은 값이 없을 경우
        statements;        
}
```



### 3항 연산식

- type 변수 = (조건식)? 값1 : 값2;

```java
boolean flag = true;

int result = (flag)? 1: -1; // 1
```



## 반복문

### for문

```java
for(초기값; 조건식; 증감식){
    // 반복처리 문장
}

int sum = 0;
for(int i=0; i<=10; i++){
    sum += i    
}
System.out.print(sum) // 55
```





### while문

```java
while(조건식){
    // 반복 처리 문장
}
```

```java
int i = 0;
int sum = 0;
while(i<10){
    sum += i;
    i++;
}
```



### do-while문

```java
do{
    // 반복 처리 문장
}while(조건식);
```

```java
do{
    Scanner scan = new Scanner(system.in);
    int num = scan.nextInt();
}while(num<10);
```



### for~each문

```java
for(type 변수 : 데이터들 ){
    // 반복 처리 문장
}
```

```java
for(int name : names){
    System.out.println(name);
}
```



## Array

### 선언

- 타입이나 변수 옆에 []사용

- int [] su;
- int su[]];



### 생성

- su = new int[50];
  - 크기를 50만큼 생성
  - 생성과 선언을 동시에 작성 可



### 값할당

- su[0] = 10;



### 다차원 Array

```java
int [][] su;
int su[][];

su = new int[5][5];

su[0][0] = 1;
```



## Operations

- 클래스내에 객체가 가져야할 기능 정의시에 사용

```java
public static return_type method_name(parameter list)
{
    // 수행할 문장들
}
```


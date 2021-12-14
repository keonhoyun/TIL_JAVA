# TIL_3weeks

## DB

### CRUD

- Insert
- update
- delete
  - 위 3개는 executeUpadte(); 메서드 이용
- select
  - executeQuery(); 메서드 이용

### 외래키





## 쓰레드(Thread)

> JVM에 있는 쓰레드 스케줄러에서 관리

> 실행문 두 개가 동시에 실행시키도록 만들어줌
>
> 쓰레드는 하나의 프로세스에서 다중 실행이 가능하다.

### class Thread

- start() 로 실행



### inerface Runable

- 상속은 하나밖에 못하므로 쓰레도 이외에 다른 클래스를 상속받을 경우 사용

- start()바로 실행 不可

  - 쓰레드 클래스 생성 必

  ```java
  public static void main(String[] args) {
      RunnableTest rt1 = new RunnableTest("first");
      RunnableTest rt2 = new RunnableTest("second");
  
      Thread t1 = new Thread(rt1);
      Thread t2 = new Thread(rt2);
      
      t1.start();
      t2.start();
  }
  ```

  

### 우선순위 설정

- setPriority

```java
t1.setPriority(Thread.MAX_PRIORITY); // 우선적으로 시작
t1.setPriority(Thread.MIN_PRIORITY); // 가장 늦게 시작
```



### 동기화(synchronized)

#### 설정

> 실행되는 동안 다른 쓰레드가 접근하지 못하게 막음
>
> 쓰레드 메서드가 실행중에는 다른 쓰레드는 대기 상태가 됨
>
> 메서드에 syncronized 키워드를 표기함
>
> 
>
> 접근제한자과 반환형 사이에 적기
>
> ```java
> public synchronized void run() {
>     for(int i=1; i<=10; i++) {
>         getMoney(1000);
>     }
> }
> ```
>
> 
>
> 메서드 안에 기입
>
> ```java
> public void run() {
>     synchronized(this){
>         for(int i=1; i<=10; i++) {
>             getMoney(1000);
>         }			
>     }		
> }
> ```



#### 해제

```java
// 동기화 해제
if(money%2000==0) {//동기화 해제
    try {
        this.wait(); // 잠시 대기
    } catch (Exception e) {}
}else {
    // 다른 쓰레드는 대기모드
    this.notify(); // 다시 동기화 시키기
}
```



## WEB

### 인터프리트 언어

- HTML
- CSS
- JAVAScript

### HTML

#### 태그

### JSP

> 서버가 없으면 실행 不可
>
> Server Language

## JAVAScript




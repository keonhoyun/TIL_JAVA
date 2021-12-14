# TIL_JDBC

## JDBC

> 응용프로그램이 데이터 베이스에 연결하여 데이터 베이스를 이용할 수 있도록 하는 자바 클래스의 모임

```java
interface DBConnect {
    void connect();
}
class OracleDBConnect implements DBConnect{
    void connect(){
        // oracle 데이터 베이스에 연결하는 방법 정의
    }
}

class SQLServerDBConnect implements DBConnect{
    void connect(){
        // SQL Server 데이터 베이스에 연결하는 방법 정의
    }
}

class Test{
    public static void main(String args[]){
        DBConnect oracle = new OracleDBConnect();
        DBConnect sqlserver = new SQLServerDBConnect();
        oracle.connect(); // OracleDBConnect 클래스의 connect() 메서드 호출
        sqlserver.connect(): // SQLServerDBConnect 클래스의 connect() 메서드 호출
    }
}
```


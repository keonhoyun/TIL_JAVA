# TIL_Ajax

## AJAX

> 언어나 프레임워크가 아닌 구현하는 방식을 의미
>
> 웹에서 화면을 갱신하지 않고 데이터를 서버로부터 가져와 처리함
>
> XHR 객체로 데이터를 전달, 비동기 방식으로 결과를 조회

> ### 일반요청
>
> data를 입력 후 event 발생
>
> Ajax를 적용하지 않은 경우 서버에서 data를 이용하여 logic처리

> ### Ajax 요청
>
> data를 입력 후 event 발생
>
> 서버에서 요청을 처리하여 Text, XML or JSON으로 응답
>
> 화면전환 없이 동적으로 화면 재구성 可能

### httpRequest 속성값

#### readyState

| 값   | 의미          | 설명                                          |
| ---- | ------------- | --------------------------------------------- |
| 0    | Uninitialized | 객체만 생성(open 메서드 호출 전)              |
| 1    | Loading       | open 메서드 호출                              |
| 2    | Loaded        | send 메서드 호출, status의 헤더가 아직 도착 X |
| 3    | Interactive   | 데이터의 일부를 받은 상태                     |
| 4    | Completed     | 데이터의 전부를 받은 상태                     |



#### status

| 값   | 텍스트                | 설명        |
| ---- | --------------------- | ----------- |
| 200  | OK                    | 요청성공    |
| 403  | Forbidden             | 접근 거부   |
| 404  | Not Found             | 페에지 없음 |
| 500  | Internal Server Error | 서버 오류   |
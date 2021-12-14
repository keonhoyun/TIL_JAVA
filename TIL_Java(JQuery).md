# TIL_JQuery

## JQuery

```html
<!-- 기본 구문 -->
$(selector).action();

<!-- $(selector)는 탐색한 DOM객체들을 담은 래퍼세트(WrapperSet)를 반환 -->
<!-- 래퍼세트(WrapperSet)를 통해 기능을 처리하는 액션 함수 호출 -->

$(document).ready(function() {
 // TODO
});
```

> jQuery는 가벼운 자바스크립트 라이브러리, DOM 조작 Ajax 지원 등을 쉽고 빠른 개발을 지원
>
> jQuery 선택자는 DOM를 탐색, 다양한 래퍼세트 객체를 반환
>
> 레퍼세트 객체는 메소드 체인을 제공, 메서드 호출에서의 반복적인 코딩을 줄여줌

### DOM 요소선택

#### 선택자

>CSS 문법을 확장해서 태그를찾는 Selector 제공
>
>특정 브라우저의 의존적인 스크립팅을 벗어 날 수 있음
>
>```html
>$("h1").css("color", "blue");
>
><!-- 요소선택자 -->
>$("*"): 모든요소
>$("#id"): id
>$("elementName"): element(태그)
>$(".Class"): class -> $("tagnName.classname"), $(".class1.class2")도 가능
>$("selector1, selector2, selector3"): Multi
>
>
><!-- 계층구조 -->
>$("Parent > Child"): 자식선택자, 인접한 하위 자식
>$("Ancestor Descendant"): 자손선택자, 모든 하위 자식
>$("Previous + Next"): 인접선택자, 인접한 바로 다음 형제
>$("Previous ~ Next"): 형제선택자, Next에 대한 모든 형제
>
><!-- 속성선택자 -->
>$(selector[attr]) attr을 속성값으로 가지는 문서객체 선택
>~= : 공백을 포함하여 Value를 포함하는 객체선택
>*= : value를 포함하는 문서객체
>^= : value로 시작함
>$= : value로 끝남
>
><!-- 필터선택자 -->
>: 사용
>el:button type이 button인 input요소 or button요소
>:first 첫번째 요소 선택
>:last 마지막 요소 선택
>:first-child 첫 번째 자식
>:only-child 형제가 없는 요소
>:even 짝수번째
>:odd 홀수번째
>
>:not(filter) 일치하지 않는 모든 요소
>:contains(str) 텍스트 str를 포함하는 요소
>:nth-child(n) n번째 자식요소(인덱스는 1부터 시작) / eq, gt, lt는 0부터 시작
>:has 주어진 선택자와 일치하는 하나 이상의 요소를 포함하는 요소
>```



#### 래퍼세트와 메서드

> ```html
> size(): 요소개수 반환
> get(index): 인덱스 번호에 위치하는 DOM객체 반환
> index(element): 해당요소의 인덱스 번호 반환
> add(expr): expr로 명시한 요소를 추가
> not(expr): expr로 명시한 요소를 제거
> each(function(index, element)) 각 요소마다 function 수행
> fillter(expr): expr에 명시한 요소를 필터링
> slice(begin, end): 현재 레퍼세트의 일부분으로 새로운 래퍼세트 생성
> ```



## DOM 객체


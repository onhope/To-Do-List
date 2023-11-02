# To-Do-List

<img src="./To Do List.gif">

## 기능
- 할일을 입력을 하면 목록이 형성     
- 리스트 체크   
- 리스트 삭제     
<br>

## 사용한 라이브러리 
**fontawesome**  
https://fontawesome.com/

<br>

## 학습  
### 1. js : webStorage - Localstorage vs sessionStorage
: **webStorage**란 클라이언트 단, <span style="background-color: black; color: white">즉 브라우저 상에 데이터를 저장할 수 있는 기술</span>

<table>
  <tr>
    <td style="font-weight:bold">속성</td>
    <td style="font-weight:bold">Localstorages</td>
    <td style="font-weight:bold">sessionStorage</td>
  </tr>
  <tr>
    <td style="font-weight:bold">차이점</td>
    <td>웹페이지의 세션이 끝나더라도 데이터가 지워지지 않음</td>
    <td >웹페이지의 세션이 끝날 때 저장된 데이터가 지워짐</td>
  </tr>
    <tr>
    <td style="font-weight:bold">공통점</td>
    <td colspan=2>모두 데이터를 브라우저 상에 저장,  자바스크립트 API가 완전히 동일한 형태</td>
  </tr>
</table>

<br>  

: 웹 스토리지는 기본적으로 키(key)와 값(value)으로 이루어진 데이터를 저장할 수 있음
```
// 키에 데이터 쓰기
localStorage.setItem("key", value);

// 키로 부터 데이터 읽기
localStorage.getItem("key");

// 키의 데이터 삭제
localStorage.removeItem("key");

// 모든 키의 데이터 삭제
localStorage.clear();

// 저장된 키/값 쌍의 개수
localStorage.length;
```
<br>

: 웹 스토리지를 사용할 때 주의해야 할 부분은 **오직 문자형(string) 데이터 타입만 지원**하므로, 다른 타입의 데이터를 저장하려고 할 때 문자형으로 변환을 해야함  
 => 이를 해결하기 위해서 **JSON 형태**로 데이터를 읽고 쓰면 됨 
```
> localStorage.setItem('json', JSON.stringify({a: 1, b: 2}))
undefined
> JSON.parse(localStorage.getItem('json'))
{a: 1, b: 2}
```
```
> localStorage.setItem('nums', JSON.stringify([1, 2, 3]))
undefined
> JSON.parse(localStorage.getItem('nums'))
[1, 2, 3]
```

<br>  

### 2. js : event.preventDefault()
: 어떤 이벤트를 명시적으로 처리하지 않은 경우, 해당 이벤트에 대한 사용자 에이전트의 기본 동작을 실행하지 않도록 지정  
: 주로 사용되는 경우는
- a 태그를 눌렀을때도 href 링크로 이동하지 않게 할 경우  
- form 안에 submit 역할을 하는 버튼을 눌렀어도 새로 실행하지 않게 하고싶을 경우 (submit은 작동됨)

<br>

### 3. js : json.stringfy()
: **JSON의 일반적인 용도**는 <span style="background-color: black; color: white">웹 서버와 데이터를 교환하는 것.</span>  
: 웹 서버에 데이터를 보낼 때 데이터는 **문자열**이어야 하는데, **JSON.stringify()를 사용하여 JavaScript 개체를 문자열로 변환**  
: JSON을 사용하면 JavaScript 개체를 텍스트로 저장할 수 있습니다.
```
<!-- 로컬 저장소에 데이터 저장하고 가져오는 방식 -->
<!DOCTYPE html>
<html>
<body>

<h2>Store and retrieve data from local storage.</h2>
<p id="demo"></p>

<script>
// Storing data:
const myObj = { name: "John", age: 31, city: "New York" };
const myJSON = JSON.stringify(myObj);
localStorage.setItem("testJSON", myJSON);

// Retrieving data:
let text = localStorage.getItem("testJSON");
let obj = JSON.parse(text);
document.getElementById("demo").innerHTML = obj.name;
</script>

</body>
</html>

```
<br>

### 4. js : classList 메서드 

|메서드|의미|
|------|---|
|add(string) | 지정한 클래스 값을 추가한다. 만약 추가하려는 클래스가 엘리먼트의 class 속성에 이미 존재한다면 무시한다.|
|remove(string) | 지정한 클래스 값을 제거한다. *: 존재하지 않는 클래스를 제거하는 것은 에러를 발생시키지 않습니다.|
|item(number) | 콜렉션의 인덱스를 이용하여 클래스 값을 반환한다.|
|toggle(string, [, force] ) | 하나의 인수만 있을 때: 클래스 값을 토글링한다. 즉, 클래스가 존재한다면 제거하고 false를 반환하며, 존재하지 않으면 클래스를 추가하고 true를 반환한다.두번째 인수가 있을 때: 두번째 인수가 true로 평가되면 지정한 클래스 값을 추가하고 false로 평가되면 제거한다.|
|contains(string) | 지정한 클래스 값이 엘리먼트의 class 속성에 존재하는지 확인한다. |
|replace(oldClass, newClass) | 존재하는 클래스를 새로운 클래스로 교체한다.


<br>

## 개선할 부분
- 수정기능 추가하기 

<br>  

## 학습출처
- 강의  
  : https://www.youtube.com/@JavaScriptKing
- localstorage  
  : https://www.daleseo.com/js-web-storage/  
- event.preventDefault()   
  : https://programming119.tistory.com/100  
  : https://developer.mozilla.org/ko/docs/Web/API/Event/preventDefault
- json.stringfy()  
  : https://www.w3schools.com/js/js_json_stringify.asp
- classList  
  : https://developer.mozilla.org/ko/docs/Web/API/Element/classList
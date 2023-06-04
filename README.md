# Kakao_Tech_React

> 6/4
	## DOM 다루기 / Element 생성하기

- CodeSandBox
    - 리액트 맛보기 동안 사용할 도구
- Vanilla js Dom
    - W3Schools / createElement
- CDN
    - unpkg
    
    [CDN 링크 – React](https://ko.legacy.reactjs.org/docs/cdn-links.html)
    
- React / React-dom
    - element 생성 / appendChild

### createElement()

```jsx
React.createElement(
    type,
    [props],
    [...children]
)
```

### render()

```jsx
ReactDOM.render(element, container[, callback])
```

## JSX

- 문자도 HTML도 아닌 JavaScript의 확장 문법

```jsx
const element = <h1>Hello,world!</h1>;
```

### Babel

- JavaScript Compiler
- 특정 언어를 다른 프로그래밍 언어로 옮기는 프로그램

![스크린샷 2023-06-04 오후 2.33.39.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7063fba1-9d35-44ff-a6ba-d602839440ab/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-06-04_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_2.33.39.png)

[Babel · Babel](https://babeljs.io/)

```jsx
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

<script type="text/babel">
        const rootElement = document.getElementById("root");
        const element = <h1 className="title">"Hello,world!</h1>
        ReactDom.render(element, rootElement);
</script>
```

### Spread 연산자 : `…`

- 객체나 배열을 확장 또는 병합할 때 사용하는 문법

```jsx
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];

console.log(arr2);
// 출력: [1, 2, 3, 4, 5]
```

## 멀티 Element 생성하기

### Fragment

- React.Fragment or <><>

## 리액트의 리랜더링

### 리랜더링

- 컴포넌트의 상태(state)나 속성(props)이 변경될 때 발생하는 과정
- React는 `변경된 부분만 실제 DOM에 업데이트`하므로 화면 전체를 다시 그리지 않는다

## fetch

- **`fetch()`** API는 네트워크를 통해 리소스를 요청하고 응답을 받아오는 메서드

### fetch api 사이트

[fetch() 전역 함수 - Web API | MDN](https://developer.mozilla.org/ko/docs/Web/API/fetch)

### api

```jsx
fetch('http://examle.com/movies.json')
  .then(response => response.json())
  .then(data => {
    console.log(data); // 응답 데이터 출력
  })
  .catch(error => {
    console.log('Error:', error); // 에러 처리
  });
```

- **`fetch()`**에 요청할 URL을 전달합니다. **`fetch()`**는 서버로부터 받은 응답을 나타내는 Response 객체를 반환
- **`then()`** 메서드를 사용하여 응답 데이터를 JSON 형식으로 변환하고, 다음 **`then()`** 메서드에서 데이터를 처리

### 예시

```jsx
const myImage = document.querySelector("img");

const myRequest = new Request("flowers.jpg");

fetch(myRequest)
  .then((response) => {
    if (!response.ok) {
      throw new Error(`HTTP 오류! 상태: ${response.status}`);
    }

    return response.blob();
  })
  .then((response) => {
    myImage.src = URL.createObjectURL(response);
  });
```

## 회고

```jsx
리액트를 처음 사용하려고 하니까 생각보다 복잡하고, 아직 리액트의 ㄹ 자도 들어가지 않았겠지만 천천히 배워보겠다. 그리고 맨날 ajax만 사용하다가 fetch를 처음 써보니까 뭔가 반가우면서도 비슷한 요청형식에 백엔드에서 http 요청이랑, OKHTTP 뭐 이런 느낌으로 여러가지 방식이 있다는걸 느꼈다. 아직 배울게 많고 공부해야할 게 많은거 같으니 천천히라도 꾸준히 하는게 중요할 거 같다 !
``` 

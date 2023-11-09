# 고양이 짤방 생성기

https://milooy.github.io/cat-jjal-maker/

> 고양이 짤방을 생성하는 리액트 앱입니다

![328234-0-resize](https://user-images.githubusercontent.com/3839771/149098995-0b89419a-58fb-494a-ade3-27aae5342553.gif)

## 연관 리액트 강의

인프런의 [만들면서 배우는 리액트: 기초](https://www.inflearn.com/course/%EB%A7%8C%EB%93%A4%EB%A9%B4%EC%84%9C-%EB%B0%B0%EC%9A%B0%EB%8A%94-%EB%A6%AC%EC%95%A1%ED%8A%B8-%EA%B8%B0%EC%B4%88) 강의에서 만드는 토이 프로젝트입니다.

![KakaoTalk_Photo_2022-01-12-18-15-08](https://user-images.githubusercontent.com/3839771/149098759-6a7b4a16-5c7f-431e-8fb5-cc750fd527a2.jpeg)



---




#### `리액트, 바벨 추가`
```js
<script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>  
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>  
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```



#### `index`
```js
<script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>  
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>  
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>  
  <script type = "text/babel">  
  
    console.log("야옹");  
  
    const catItem =(  
            <li>  
              <img src="https://cataas.com/cat/HSENVDU4ZMqy7KQ0/says/react"/>  
            </li>  
    );  
  
    const 여기다가그려 = document.querySelector('#app');  
    ReactDOM.createRoot(여기다가그려).render(catItem);  
  </script>  
</body>
```




### babel

1. React는 바벨을 통해 JSX를 `'React.createElement'` 형식의 자바스크립트로 변환한다.
2. 브라우저에서는 변환된 코드를 확인할 수 있다.
3. 웹 페이지의 '`head`' 부분에는 바벨이 추가한 스크립트가 있다.
4. 이 스크립트는 브라우저가 이해할 수 있는 자바스크립트로 변환된 코드를 포함하고 있다.
6. 바벨은 이 과정을 가능하게 해주는 핵심 도구다.

즉, 바벨은 우리가 React를 사용하여 편리하게 웹 페이지를 작성할 수 있도록 도와주는 도구이다. 이를 통해 React는 브라우저가 이해할 수 있는 코드로 변환되며, 이것이 바로 바벨이 하는 역할.



### **7 JSX로 HTML과 JavaScript 짬뽕하기**

1. React에서는 최상위 태그가 하나만 있어야 한다. 만약 최상위 태그가 두 개 이상이면 에러가 발생한다.
2. 이 에러를 해결하려면, 최상위 태그를 하나로 묶는다.
3. 저장 후 확인해보면, 에러가 해결되었음을 확인할 수 있다.

### `index.html`
```js
    <!--  리액트와 바벨 추가는 필수-->

    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>

    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

    <script type="text/babel">

        console.log("야옹");
        // const catItem = (
        //     <li>
        //         <img src="https://cataas.com/cat/HSENVDU4ZMqy7KQ0/says/react" />
        //     </li>
        // );

        const FOO = " hello world ";
        const favorites = (
            <ul className="favorites">
                {catItem}
                {catItem}
                {catItem}
            </ul>
        );
        const mainCard = (
            <div class="main-card">
                <img
                    src="https://cataas.com/cat/HSENVDU4ZMqy7KQ0/says/react"
                    alt="고양이"
                    width="400"
                />
                <button>🤍</button>
            </div>
        );
        const app = (
            <div>
                {mainCard}
                {favorites}
                {h1}
                {im}
            </div>
        );
        const h1 = (
            <h1>1번째 고양이 가라사대</h1>
        );
        const im = (
            <form>
                <input type="text" name="name" placeholder="영어 대사를 입력해주세요" />
                <button type="submit">생성</button>
            </form>
        );
        const 여기다가그려 = document.querySelector('#app');
        ReactDOM.createRoot(favorites, 여기다가그려).render(catItem);
    </script>
</body>
```






---


* `React`에서 인자를 넘길때 Props라고 부른다.
* `React` 에서는 바로 값을 넘길때는 `props.childern`을 사용한다.

```js
const app = (  
    <div>  
        <Title>공양</Title>  
        <Form/>        <MainCard>https://cataas.com/cat</MainCard>  
        <Favorites/>    </div>  
);
```

```js
const Title = (props) => {  
    return (  
        <h1>{props.children}</h1>  
    )  
}
```

* 중괄호 추가하면 props 를 스킵할 수 있다.
  ![](../../../../3Resource/assiset/image1109.png)


### 12 스타일링

- 클래스네임을 사용하는 방식: HTML의 'class' 대신 리액트에서는 'className'을 사용한다. 이는 리액트 태그가 HTML 태그와 약간 다르기 때문이다.
- 인라인 스타일링: 'style' prop에 객체를 넘겨 스타일링을 한다. 이 때, 객체의 값은 문자열로 넘겨야 한다.
- 라이브러리를 사용하는 방식: 'emotion'이나 'tailwind.css'와 같은 라이브러리를 사용해 스타일링을 할 수 있다.


### 13 이벤트 리스트

1. 리액트에서 이벤트를 다루는 방식은 컴포넌트의 특정 행동에 대응하여 코드를 실행한다. 이벤트 리스너는 특정 이벤트(예: 클릭, 마우스 오버 등)가 발생할 때 호출되는 함수가 된다.

2. 이벤트 핸들러 함수는 일반적으로 '`handle`'이라는 접두사로 시작하며, 이는 '이벤트를 처리한다'는 의미를 가진다.

3. 리액트에서는 이벤트 핸들러를 속성으로 전달할 때 `'on<EventName/>'` 형식을 사용한다. 예를 들어, 클릭 이벤트를 처리하는 핸들러는 'onClick', 마우스 오버 이벤트를 처리하는 핸들러는 '`onMouseOver`' 등으로 전달한다.

4. 이벤트 핸들러 함수 내에서는 이벤트 객체를 인자로 받을 수 있고, 이 객체를 통해 이벤트의 정보에 접근할 수 있다. 예시로, '`event.preventDefault()`' 메서드를 호출하면 이벤트의 기본 동작을 막는다.

5. 폼의 '`submit`' 이벤트는 기본적으로 페이지를 새로고침한다. 이를 방지하기 위해 이벤트 핸들러에서 '`event.preventDefault()`'를 호출한다.

```js
const Form = () => {  
    function handleFormSubmit(){  
        console.log( "폼 전송됨 " );  
    }  
    return (  
        <form onSubmit ={handleFormSubmit}>  
            <input  
                type="text"  
                name="name"  
                placeholder="영어 대사를 입력해주세요"  
            />  
            <button type="submit">생성</button>  
        </form>  
    )  
}
```


### 14 상태 함수 useState

> useState는 리액트의 상태 관리 기능 중 하나로, 이를 통해 컴포넌트 내에서 동적인 값을 유지하고 변경할 수 있다. 이 값은 사용자의 입력, API 응답 등에 따라 변할 수 있는 값이다.

1. 리액트에서 상태를 만들고 관리하는 방법은 `useState` 함수를 사용하는 것이다.

    - `useState` 함수에 첫 번째 인자로 상태의 초기값을 설정한다.
    - `useState` 함수는 배열을 반환하며, 첫 번째 요소는 현재 상태, 두 번째 요소는 상태를 업데이트하는 함수이다.
2. 상태 업데이트 함수(`setState`)를 사용하여 상태를 변경할 수 있다. 이 함수는 새로운 상태 값을 인자로 받아 상태를 업데이트한다.

```js
const [counter, setCounter] = React.useState(1);  
  
  
console.log("카운터", counter);  
function handleFormSubmit(event){  
    event.preventDefault();  
    console.log( "폼 전송됨 " );  
    setCounter(counter + 1);  
}
```

> 상태 업데이트 함수를 사용할 때는 기존 상태 값에 기반해 새 상태 값을 계산할 수도 있다. 이를 통해 이전 상태 값을 기반으로 새 값을 계산하는 로직을 구현할 수 있다.




### 상태 State  끌어올리기

> 상태를 어떻게 다루고, 어떻게 상태를 끌어올릴 수 있는지를 이해하는 것.
> 상태를 어디에 위치시키는 것이 좋을지, 어떻게 상태를 재사용할 수 있는지에 대한 고민도 중요하다.

"상태 끌어올리기(`Lifting State Up`)"라는 개념에 대해 설명한다.
상태 끌어올리기는 상태를 자식 컴포넌트에서만 사용하던 것을 부모 컴포넌트에서도 사용하게 만드는 방법이다.

```js
function handleFormSubmit(event) {  
  event.preventDefault();  
  console.log("폼 전송됨");  
  setCounter(counter + 1);  
}
```

이를 구현하기 위해서는 먼저 상태를 부모 컴포넌트로 옮긴다.
이렇게 하면 자식 컴포넌트에서도 상태에 접근할 수 있다.

다음으로, 상태를 변경하는 함수를 부모 컴포넌트로 옮긴다.
이 함수는 자식 컴포넌트에서 호출되며, 부모 컴포넌트의 상태를 변경한다.

```js
const App = () => {  
    const [counter, setCounter] = React.useState(1);  
  
    console.log("카운터", counter);  
  
    function handleFormSubmit(event) {  
        event.preventDefault();  
        console.log("폼 전송됨");  
        setCounter(counter + 1);  
    }  
  
   ...
};
```

마지막으로, 부모 컴포넌트에서 자식 컴포넌트로 상태와 함수를 props를 통해 전달한다. 이렇게 하면 자식 컴포넌트에서도 부모 컴포넌트의 상태를 변경할 수 있다.

이번 강의에서는 이러한 개념을 통해 '`생성`' 버튼을 누르면 카운터가 증가하고, 그에 따라 고양이의 이미지가 변경되는 기능을 구현한다.







































































































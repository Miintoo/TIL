# 2023-02-08 

## 1. 화살표 중복 함수

```js
const handleCheckboxChange = pathFn => e => {
    const name = e.target.name;
    if (e.target.checked) {
      // filter를 추가합니다.
      return setFilters(filterObj => ({ ...filterObj, [name]: pathFn }));
    }
}
```

화살표가 중복돼서 사용되는 함수의 경우에는

```js
const handleCheckboxChange = pathFn => {
    return (e) => {
        const name = e.target.name;
        if (e.target.checked) {
          // filter를 추가합니다.
          return setFilters(filterObj => ({ ...filterObj, [name]: pathFn }));
        }
    }
}

```

위 코드처럼 함수 내부에서 함수를 return 값으로 작성하고 싶을 경우 사용한다고 보면 된다.

## 2. search 함수

```js

const test1 = "hello world";

console.log(test1.search("h"); // 0

```

search 함수의 경우에는 문자열에서 인자에 해당하는 언소가 있을 경우 해당 위치를 return 해주는 함수이다. 
만일 해당 값이 없을 경우에는 -1을 return 한다.

# 2023-02-10

## 서버 post 요청

서버에게 데이터를 보내는 post 요청은 js의 객체를 그대로 보내도 못쓰기 때문에 JSON화 해서 보내는게 좋다. 

```js
const bodyData = JSON.stringify(data);

await axios.post(serverURL, bodyData);
```

## && 연산자

A && B && C

세가지 데이터가 있다면 A가 true 여야 다음으로 넘어가고 B가 true여야 C가 결과값이 되는 구조로 되어져 있다.
앞에 데이터가 false라면 거기서 해당 로직은 멈춘다.

true && <MyComponent />

앞의 결과가 true여야 뒤에 컴포넌트가 실행되도록 로직을 짤 수 있다.

## 버튼의 disabled 기능

버튼태그에 속성값중 disabled=true 라면 해당 버튼이 비활성화 되어서 클릭이 불가능하게 만들 수 있다.

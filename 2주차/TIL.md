# 2023-01-10

## 1. 클라이언트와 서버란?

클라이언트는 request를 보내는 곳 
서버는 response를 해주는 곳
으로 이해하면 되고 서버도 다른 서버에 request를 보낼때는 클라이언트가 될 수 있다.

# 2023-01-15

## 1. useEffect의 dependancy 

### useEffect 동작원리

useEffect의 동작 원리는 처음에 mount 됐을 때 콜백이 한 번 호출되고 두번째 인자인 dependancy array의 각 element 값이 변경됐을 때 콜백이 한 번더 호출된다.

### dependancy array의 각 element의 값이 변경되는지 판단되는 시점은 언제일까?

컴포넌트가 랜더링되는 시점이다. 
컴포넌트가 랜더링 될 때마다 선언해 놓은 useEffect함수가 실행되고 내부 콜백 함수와 dependancy array가 파라미터로 전달된다. 그러면 useEffect 내부 로직에 의해 
dependancy array를 캐싱하고 있고 이전 각 element를 반복하면서 dependancy array의 element와 비교한 뒤 다르면 첫 번째 파라미터인 콜백을 호출하는 구조로 되어져있다.

그래서 dependancy array 를 빈 배열로 넣어놓으면 한 번만 useEffect가 호출 되는것이다.


# 2023-02-08 

## 1. 화살표 중복 함수

```
const handleCheckboxChange = pathFn => e => {
    const name = e.target.name;
    if (e.target.checked) {
      // filter를 추가합니다.
      return setFilters(filterObj => ({ ...filterObj, [name]: pathFn }));
    }
}
```

화살표가 중복돼서 사용되는 함수의 경우에는

```
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

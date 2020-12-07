# 반복문(For)

## 기본 반복문
```js
for(let i = 0; i < array.length; i++){
    let idx = i;
    let val = array[i];
}
```

## for in 반복문과 for of 반복문

- 객체에 쉽게 반복문을 적용함
- for in 반복문과 for of 반복문은 for 반복문 사용과 역할이 같음
- iterables vs enumerables
  - enumerables : 순서 없음
    - `for in`
  - iterables : 순서 있음, enumerables의 부분 집합
    - `for of`
### for in 반복문

> for in 형식

```js
for(let 인덱스 in 배열){

}
```

> for in 예제

```js
for(let i in array){
    console.log(`${i}번째 요소 : ${array[i]}`);
}
```

### for of 반복문

> for of 형식

```js
for(let 요소 of 배열){

}
```

> for of 예제

```js
for(let item of array){
    console.log(item);
}
```
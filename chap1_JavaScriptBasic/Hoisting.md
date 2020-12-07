# 호이스팅(Hoisting)

`Hoisting의 사전적 의미`
> 끌어 올리기, 들어올려 나르기

``` js
console.log(a);
var a = 'Hello World!';
```
- 호이스팅에 의해 위의 코드가 가능
- 변수가 아래쪽에 선언 되어 있어도 위로 끌어 올려져서 아래와 같은 형식으로 논리적으로 바뀌에 뒨다.

``` js
var a;
console.log(a);
a = 'Hello World!';
```
- 콘솔에 `undefined`이 출력 된다.
- 실제로벌어지는일
  - 물리적으로 code가 옮겨지는 것이 아님
  - 변수와 함수의 선언(declaration)이 Lexical Environment에 추가 됨.(식별자-변수/ 함수mapping을 저장하는 자료구조)
    - Lexical Environment : 변수나 함수의 `이름`들이 실제 어떤 메모리에 매핑이 되는지 저장하는 자료 구조

## let의 호이스팅
let은 선언시에 호이스팅이 적용된다.
* `선언 -> TDZ(Temporal Dead Zone) ->  초기화 -> 사용`
```js
let a = 1;
{
    console.log(a);
    let a = 2;
} 
```
> 결과 :` 에러 - Uncaught ReferenceError: Cannot access 'a' before initialization`
  - 출력이 블록안의 a로 출력이 되야 맞다고 판단하는 데, 블록 안에 a가 console전에 없음으로 에러가 발생한다.


## var의 호이스팅
var을 선언시에 undefined로 지정되어 진행된다.
* `선언 -> 초기화 -> 사용`
```js
var a = 1;
{
    console.log(a);
    var a = 2;
} 
```
> 결과 : `1`
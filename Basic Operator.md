> [The Swift Language Guide](https://jusung.gitbook.io/the-swift-language-guide/language-guide/02-basic-operators)를 참조하여 공부한 내용을 정리했습니다. <br>
>> <span style="color:black">Contents
>>1. [Basic Operater](#Basic-Operator)<br>
>>2. [Terminology](#Terminology)<br>
>>2-1. [Unary Operator](#Unary-Operator)<br>
>>2-2 [Binary Operator](#Binary-Operator)<br>
>>2-3 [Ternery Operator](#Ternary-Operator)<br>
>>3. [Assignment Operator](#Assignment-Operator)<br>
>>4. [Arithmetic Operators](#Arithmetic-Operators)<br>

# Basic Operator

Swift에서의 기본연산자(Basic Operator)는 __산술연산자__(`+`, `-`, `/`, `%`), __논리연산자__(`&&`, `||`), __범위 연산자__(`a...b`)를 지원하고 있습니다.

## Terminology
### Unary Operator

__단항 연산자(unary)__는  `-a`, `!b`, `c!`와 같이 단일 대상에 대한 연산자입니다. __단항 접두사(prefix)__는 `!b`와 같이 대상의 앞에 나타나며 __단항 접미사(suffix)__는 `c!`와 같이 대상 바로 뒤에 나타납니다.

단항 연산자 종류 | 연산자 | 피연산자 수
:---:|:---:|:---:
부호 연산자 | +(양수), -(음수) | 단항
증감 연산자 | ++(1증가) --(1감소)| <span style="color:red">**`Swift 3부터 삭제`**
논리 연산자 | !(부정) | 단항도 있고 이항도 있음
비트 연산자 |  ~ | 단항도 있고 이항도 있음

### Binary Operator
**이항 연산자(Binary)**는 `1+2`와 같이 두개의 대상 사이에 위치한 연산자입니다. 

이항 연산자 종류 | 연산자 | 피연산자 수
:---:|:---:|:---:
산술 연산자| +(더하기), -(빼기), *(곱하기), /(나누기), %(나머지)  | 이항
비교 연산자 | ==, !=, >, <, =>, <= | 이항
논리 연산자 | &&, \|\| | 단항도 있고 이항도 있음
비트 연산자 | &, \|, ^ | 단항도 있고 이항도 있음
쉬프트 연산자 |  >>, <<, >>> | 이항

### Ternary Operator 
**삼항 연산자(Ternary)**는 세 개의 대상에 대한 연산으로 `a ? b : c `이 연산자만 존재합니다. ( a에 대한 조건이 참인 경우 b, 거짓인 경우 c가 실행됨 )

## Assignment Operator
**할당 연산자(Assignment)**는 값을 초기화 시키거나 변경합니다.

```swift
let a = 5		// let : 선언시 처음 입력된 데이터만 저장 가능
var b = 10		// var : 선언시 처음입력된 데이터 이후 추가로 데이터 저장 가능
b = a			// a = b 는 오류 발생
// b 값은  5 
```

여러 개의 값을 가진 튜플이면, 원소들을 여러 개의 변수나 상수로 할당할 수 있습니다.

```swift
let(x, y) = (1, 2)		// x는 1,  y는 2로 할당
```

C나 Objective-C와 다르게 Swift에서는 할당 연산자 값을 반환하지 않습니다.

```swift
if x = y { 
	// x = y 는 값을 반환하지 않기 때문에 이 코드는 오류가 발생합니다.
}
```

할당 연산자가 값을 반환하지 않는 이유는 동등비교연산자(==)를 사용해야 하는 곳에 할당연산자(=)가 실수로 사용되는 것을 막기 위해서 Swift에서는 지원하지 않습니다.

## Arithmetic Operators
모든 숫자 형에서 사용 가능한 4가지 **표준 산술 연산자(Arithmetic)**를 지원합니다.

* 덧셈 ( + )
* 뺄셈 ( - )
* 곱셉 ( * )
* 나눗셈 ( / )

```swift
3 + 7		// 10
4 - 2		// 2
3 * 3		// 9
12.0 / 3.0		// 4.0
```

C 와 Objective-C의 산술 연산자와 달리, Swift산술 연산자는 기본적으로 **값 넘침(Overflow)**를 허용하지 않습니다. 다만 `a &+ b`와 같은 **값 넘침 연산자(Overflow Operator)**를 사용하면 가능합니다.

덧셈 연산자는 문자열(String) 이어붙이기도 지원합니다.

```
"hello " + "world"		// hello world 출력
```

### Remainder Operator
**나머지 연산자(Remainder)**는 `a % b`와 같이 a를 b로 나눴을때 나머지 값을 반환합니다.

```swift
 13 % 6		// 1
-13 % 6		// -1
```


![](https://user-images.githubusercontent.com/37801676/135037489-66353835-fd4e-45ef-92c7-c780310df89f.png)
작업 방법은 `16 % 4`를 계산하기 위해서는 `16`안에 `6`을 몇번 채워 넣을지 알아야 합니다.
`13`에 `6`을 두번 채울 수 있고, 나머지가 `1`니다.
<br>
`a % b`에 대한 답을 결정하기 위해, `%`연산자는 다음 방정식을 계산합니다.

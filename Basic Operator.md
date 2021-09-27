> [The Swift Language Guide](https://jusung.gitbook.io/the-swift-language-guide/language-guide/02-basic-operators)를 참조하여 공부한 내용을 정리했습니다. <br>
>> <span style="color:black">Contents
>>1. [Basic Operater](#BasicOperator)<br>
>>2. [Terminology](#Terminology)<br>
>>2-1. [Unary Operator](#UnaryOperator)<br>
>>2-2 [Binary Operator](#BinaryOperator)<br>
>>2-3 [Ternery Operator](#TernaryOperator)<br>
>>3. [Assignment Operator](#AssignmentOperator)<br>

# Basic Operator

Swift에서의 기본연산자(Basic Operator)는 **산술연산자**(`+`, `-`, `/`, `%`), **논리연산자**(`&&`, `||`), **범위 연산자**(`a...b`)를 지원하고 있습니다.

## Terminology
### Unary Operator

**단항 연산자(unary)**는  `-a`, `!b`, `c!`와 같이 단일 대상에 대한 연산자입니다. **단항 접두사(prefix)**는 `!b`와 같이 대상의 앞에 나타나며 **단항 접미사(suffix)**는 `c!`와 같이 대상 바로 뒤에 나타납니다.

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

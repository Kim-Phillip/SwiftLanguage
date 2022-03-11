> [The Swift Language Guide](https://jusung.gitbook.io/the-swift-language-guide/language-guide/02-basic-operators)를 참조하여 공부한 내용을 정리했습니다. <br>
>> <span style="color:black">Contents
>>1. [Basic Operater](#Basic-Operator)<br>
>>2. [Terminology](#Terminology)<br>
>>2-1.	[Unary Operator](#Unary-Operator)<br>
>>2-2.	[Binary Operator](#Binary-Operator)<br>
>>2-3.	[Ternery Operator](#Ternary-Operator)<br>
>>3. [Assignment Operator](#Assignment-Operator)<br>
>>4. [Arithmetic Operators](#Arithmetic-Operators)<br>
>>4-1.	[Remainder Operator](#Remainder-Operator)<br>
>>4-2.	[Unary Minus Operator](#Unary-Minus-Operator)<br>
>>4-3.	[Unary Plus Operator](#Unary-Plus-Operator)<br>
>>5. [Compound Assignment Operators](#Compound-Assignment-Operators)<br>
>>6. [Comparison Operators](#Comparison-Operators)<br>
>>7. [Ternary Conditional Operator](#Ternary-Conditional-Operator)<br>
>>8. [Nil-Coalescing Operator](#Nil-Coalescing-Operator)<br>
>>9. [Range Operator](#Range-Operator)<br>
>>9-1. [Closed Range Operator](#Closed-Range-Operator)<br>
>>9-2. [Half-Open Range Operator](#Half-Open-Range-Operator)<br>
>>9-3. [One-Side Ranges](#One-Side-Ranges)<br>
>>10. [Logical Operators](#Logical-Operators)<br>
>>10-1. [Logical NOT Operator](#Logical-NOT-Operator)<br>
>>10-2. [Logical AND Operator](#Logical-AND-Operator)<br>
>>10-3. [Logical OR Operator](#Logical-OR-Operator)<br>
>>10-4. [Combining Logical Operators](#Combining-Logical-Operators)<br>
>>10-5. [Explicit Parentheses](#Explicit-Parentheses)<br>

# Basic Operator

Swift에서의 기본연산자(Basic Operator)는 산술연산자(`+`, `-`, `/`, `%`), 논리연산자(`&&`, `||`), 범위 연산자(`a...b`)를 지원하고 있습니다.

## Terminology
### Unary Operator

단항 연산자(unary Operator)는  `-a`, `!b`, `c!`와 같이 단일 대상에 대한 연산자입니다. 단항 접두사(unary prefix)는 `!b`와 같이 대상의 앞에 나타나며, 단항 접미사(unary suffix)는 `c!`와 같이 대상 바로 뒤에 나타납니다.

단항 연산자 종류 | 연산자 | 피연산자 수
:---:|:---:|:---:
부호 연산자 | +(양수), -(음수) | 단항
증감 연산자 | ++(1증가) --(1감소)| <span style="color:red">**`Swift 3부터 삭제`**
논리 연산자| !(부정) | 단항도 있고 이항도 있음
비트 연산자 |  ~ | 단항도 있고 이항도 있음

### Binary Operator
이항 연산자(Binary Operator)는 `1+2`와 같이 두개의 대상 사이에 위치한 연산자입니다. 

이항 연산자 종류 | 연산자 | 피연산자 수
:---:|:---:|:---:
산술 연산자| +(더하기), -(빼기), *(곱하기), /(나누기), %(나머지)  | 이항
비교 연산자 | ==, !=, >, <, =>, <= | 이항
논리 연산자 | &&, \|\| | 단항도 있고 이항도 있음
비트 연산자 | &, \|, ^ | 단항도 있고 이항도 있음
쉬프트 연산자 |  >>, <<, >>> | 이항

### Ternary Operator 
삼항 연산자(Ternary Operator)는 세 개의 대상에 대한 연산으로 `a ? b : c `이 연산자만 존재합니다. ( a에 대한 조건이 참인 경우 b, 거짓인 경우 c가 실행됨 )

## Assignment Operator
할당 연산자(Assignment Operator)는 값을 초기화 시키거나 변경합니다.

```swift
let a = 5		// let : 선언시 처음 입력된 데이터만 저장 가능 (constant : 상수, 실무에서 많이 사용하는 것을 권장함)
var b = 10		// var : 선언시 처음입력된 데이터 이후 추가로 데이터 저장 가능 (variable : 변수)
b = a			// a = b 는 오류 발생
// b 값은  5 
```

여러 개의 값을 가진 튜플이면, 원소들을 여러 개의 변수나 상수로 할당할 수 있습니다.

```swift
let(x, y) = (1, 2)		// x는 1,  y는 2로 할당
```

Objective-C와 다르게 Swift에서는 할당 연산자 값을 반환하지 않습니다.

```swift
if x = y { 
	// x = y 값을 반환하지 않기 때문에 오류가 발생합니다.
}
```

할당 연산자가 값을 반환하지 않는 이유는 동등비교연산자(==)를 사용해야 하는 곳에 할당연산자(=)가 실수로 사용되는 것을 막기 위해서 Swift에서는 지원하지 않습니다.

## Arithmetic Operators
모든 숫자 형에서 사용 가능한 4가지 표준 산술 연산자(Arithmetic Operators)를 지원합니다.

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

C 와 Objective-C의 산술 연산자와 달리, Swift산술 연산자는 기본적으로 값 넘침(Overflow)를 허용하지 않습니다. 다만 `a &+ b`와 같은 값 넘침 연산자(Overflow Operator)를 사용하면 가능합니다.

덧셈 연산자는 문자열(String) 이어붙이기도 지원합니다.

```swift
"hello " + "world"		// hello world 출력
```

### Remainder Operator
나머지 연산자(Remainder Operator)는 `a % b`와 같이 a를 b로 나눴을때 나머지 값을 반환합니다.

```swift
 13 % 6		// 1
-13 % 6		// -1
```


![](https://user-images.githubusercontent.com/37801676/135037489-66353835-fd4e-45ef-92c7-c780310df89f.png)
작업 방법은 `16 % 4`를 계산하기 위해서는 `16`안에 `6`을 몇번 채워 넣을지 알아야 합니다.<br>
`13`에 `6`을 `2`번 채울 수 있고, 나머지가 `1`입니다.<br>
<br>
`a % b`에 대한 답을 결정하기 위해, 나눗셈 연산자(Remainder Operator)는 다음 방정식을 계산합니다.<br>
<br>
`a` = (`b`×`승수`) + `나머지`<br><br>
`승수`는 a 안을 채울 b의 가장 큰 배수입니다.<br><br>
이 방정식에 `13`과 `6`을 집어 넣으면 다음을 산출합니다.<br><br>
`13` = (`6`×`2`) + `1`<br><br>
`a`가 음수 값일 때의 나머지 계산에도 똑같이 적용합니다.<br><br>
`-13` = (`6`×`-2`) + `-1` (`b`가 음수일 때는 `b`의 부호를 무시합니다.)<br><br>

### Unary Minus Operator
숫자 값은 `-`접두사로 표현되는 단항 음수 연산자(Unary Minus Operator)에 의해 부호가 전환할 수 있습니다.

```swift
let two = 2
let minusTwo = -two
let plusTwo = -minusTwo
```
단항 음수 연산자(Unary Minus Operator)는 어떤 공백도 없이 연산 값 바로 앞에 붙입니다.

### Unary Plus Operator
단항 양수 연산자(Unary Plus Operator)`+`는 어떤 것도 바꾸지 않고 연산 값을 반환한다.

```swift
let minusFive = -5
let minusFive = +minusFive
```
단항 양수 연산자(Unary Plus Operator)는 어떤 것도 안하지만, 음수에서 단항 음수 연산자를 사용할 때 코드 대칭성을 위해 사용할 수 있습니다.

## Compound Assignment Operators
합성 할당 연산자(Compound Assignment Operator)는 할당 연산(`=`)에 또 다른 연산과 조합해 사용하는 것을 말합니다. ex) 덧셈 할당 연산자(Addition Assignment Operator)는 `+=`로 사용할 수 있습니다.

```swift
var a = 5
a += 3		// five는 8이 됩니다.
```

`a += 3` 이라는 표현식은 `a = a + 3`을 줄인 것으로 덧셈과 할당을 조합하여 수행한 것입니다.

## Comparison Operators
Swift에서는 다음의 비교 연산자(Comparison Operators)를 지원합니다.

* 같다 (equal to; `a == b`)
* 같지않다 (not equal to `a != b`)
* 크다 (greater than; `a > b`)
* 작다 (less than; `a < b`)
* 크거나 같다 (greater than or equal to; `a >= b`)
* 작거나 같다 (less than or equal to; `a <= b`)

> Swift에서는 객체 비교를 위해 식별 연산자(Identity Operators; `===`와 `!==`)를 제공합니다.

각 비교 연산자(Comparsion Operators)는 참(`true`) 혹은 거짓(`false`) 값을 반환합니다.

```swift
1 == 1		// true (1과 1은 같기 때문)
2 != 1		// true (2와 1은 같지 않기 때문)
2 > 1			// true (2는 1보다 크기 때문)
1 < 2			// true (1은 2보다 작기 때문)
1 >= 1		// true (1은 1보다 크거나 같기 때문)
2 <= 1		// false (2는 1보다 작거나 같지 않기 때문)
```

비교 연산자(Comparsion Operators)는 if-else문 같은, 조건문에서 자주 사용 됩니다.

```swift
let name = "phillip"
if name == "phillip" {
		print("hello, world")
}	else {
		print(" I'm sorry \(name), but I don't recognize you")
}		// name이 phillip과 같기 때문에 "hello, world"를 출력합니다.
```

같은 타입의 값을 갖는 두 개의 튜플(Tuple)를 비교 할 수 있습니다. 튜플의 비교는 왼쪽에서 오른쪽 방향으로 이뤄지고 한번에 한개의 값만 비교합니다. 다른 두 값을 비교할때 까지 수행합니다.

```swift
(1, "zebra") < (2, "apple")		// true (1이 2보다 작아 zebra와 apple 비교하지 않음)
(3, "apple") > (3, " bird")		// true (3은 3과 같기 때문에 apple과 bird를 비교함; 알파벳 순서대로 비교하여 같지 않을때까지 비교)
(4, "dog") == (4, "dog")		// true (4와 4가 같기 때문에 dog와 dog를 비교함)
```

튜플(Tuple)은 비교 연산자(Comparsion Operators)가 해당 값을 비교할 수 있을 경우에만 수행합니다.

```swift
("blue", -1) < (puple", 1)		//true (비교가능함)
("blue", false) < ("purple", true)	//error (Boolean값은 연산자로 비교 불가)
```

> Swift 표준 라이브러리에서는 7개 요소 미만을 갖는 튜플만 비교할 수 있습니다. 그 이상의 요소를 갖는 튜플을 비교하려면 직접 비교 연산자를 구현해야 합니다.


## Ternary Conditional Operator

삼항 조건 연산자(Ternary Conditional Operator)는 `question ? answer1 : answer2`의 구조를 갖습니다. 그래서 `question`이 참이면 `answer1` 값을 반환하고, 거짓이면 `answer2` 값을 반환합니다.

삼항 조건 연산자는 아래 코드로 나타낼 수 있습니다. 

```swift 
if question {
	answer1
} else {
	answer2
}
```

ex) 열(row)이 제목 행(hasHeader)이면 컨텐츠 높이(contentHeight)보다 50만큼 더 크며 , 제목 행이 아니면 20만큼 더 큽니다.

```swift
let contentHeight = 40
let hasHeader = true
let rowHeight = contentHeight + (hasHeader ? 50 : 20)	//rowHeight = 90
```
위 삼항 조건 연산을 아래 코드로 나타낼 수 있습니다.

```swift
let contentHeight = 40
let hasHeader = true		// 제목 행(true)
let rowHeight: Int		// 정수형으로 등록
if hasHeader {
	rowHeight = contentHeight + 50
} else {
	rowHeight = contentHeight + 20 	
}		// rowHeight = 90
```
삼항 조건 연산자는 코드를 짧게 만들어 효율성과 가독성을 높여줍니다. 
※) 주의할 점은 이해하기 어려운 코드를 만들 수 있습니다.

## Nil-Coalescing Operator
### Optional
옵셔널(Optional)은 Swift가 가지고 있는 가장 큰 특징 중 하나로 직역하면 `선택적인`이라는 뜻입니다.
해석하면 값이 있을 수도 있고 없을 수도 있다는 것 입니다. 
예로 `a`에 `"가나다"`가 있으면 문자열이듯 `" "` 값이 비어있어도 값이 있는 문자열입니다 .
이것을 `nil`이라고 합니다. 

-
Nil 병합 연산자(Nil-Coalesciong Operator)는 `a ?? b` 형태를 갖는 연산자 입니다.
옵셔널 `a`를 벗겨서(unwraps) `nil`인 경우 `b`를 반환합니다.
  
Nil 병합 연산자는 아래 코드로 나타낼 수 있습니다.

```swift
a != nil ? a! : b 
```
삼항 조건 연산자와 `a!(unwraps)`를 사용하여 `a`가 `nil`이 아닐 경우  `a`의 값에 접근하고, `nil`일 경우 `b`를 반환합니다. 이를 단락-회로 계산(short-circuit evaluation)이라고 합니다.

아래 예제는 Nil 병합 연산자로 기본 색상 이름과 사용자가 옵션으로 정의한 색상 이름 중 하나를 선택합니다.

```swift
let defaultColorName = "red"
var userDefinedColorName: String?		// userDefinedColorName = nil

var colorNameToUse = userDefinedColorName ?? defaultColorName		// colorNameToUse = "red" 
```
```swift
userDefinedColorName = 'green'
colorNameToUse = userDefinedColorName ?? defaultColorName		// userDefinedColorName이 nil이 아니므로, colorNameToUse를 "green"으로 설정함 
```

## Range Operator
범위 연산자(Range Operators)는 값의 범위를 표현하는 방법으로, 여러 개의 방법을 가집니다.  
###Closed Range Operator
닫힌 범위 연산자(Closed Range Operator)는 `(a..b)`의 형태로 `a`에서 `b`의 범위를 정의하며, `a`와 `b`를 포함합니다. (`a`는 `b`보다 크면 안됩니다.)

```swift
for index in 1...5 {
	print("\(index) times  is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```
닫힌 범위 연산자는 `for-in`반복문 같이 모든 모든 값을 사용하고 싶은 범위를 반복할 때 유용합니다.

### Half-Open Range Operator
반 닫힌 범위 연산자(Half-Open Range Operator)는 `(a..<b)`의 형태로 `a`에서 `b`의 범위를 정의하며, `a`는 포함하지만 `b`는 포함하지 않습니다. (`a`값은 `b`보다 크면 안됩니다.)

```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0...<count {
	print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brain
// Person 4 is called Jack	
```

### One-Side Ranges
단방향 범위 연산자(One-Side Ranges)는 `[a..]` `[..a]`의 형태로 범위의 시작 혹은 끝만 지정해 사용하는 연산자이며, 지정한 시작 값 혹은 끝 값은 범위에 포함됩니다. 

```swift
let name = ["Anna", "Alex", "Brian", "Jack"]
for name in name[2...] {
	print(name)
}
// Brian
// Jack 

for name in names [...2] {
	]print(name)
}
// Anna
// Alex
// Brian
```
반 닫힌 연산자는 다음과 같이 설정 값이 범위에 포함되지 않습니다. 

```swift
let name = ["Anna", "Alex", "Brian", "Jack"]
for name in name[..<2] {
	print(name)
}
// Anna
// Alex 
```
단방향 범위 연산자는 아래와 같이 특정 값을 포함하는지 여부를 확인할 떄도 사용가능합니다.

```swift
let range = ...5
range.contains(7)	// false
range.contains(4)	// true
range.contains(-1)	// true
```

## Logical Operators
논리 연산자(Logical Operators)는 `true`와 `false`라는 불리언(Boolean) 논리 값을 연산자으로 스위프트에서는 세가지 표준 논리 연산자를 지원합니다. 

*  논리 부정 NOT (`!a`) 
*  논리 곱 AND (`a && b`)
*  논리 합 OR(`a || b`)

## Logical NOT Operator
논리 부정 연산자(Logical NOT Operator,`!a`)는 불리언 논리 값을 거꾸로 만들어 `true`는 `false`가 되고, `false`는 `true`가 됩니다.

```swift
let allowedEntry = false
if !allowedEntry {
	print("ACCESS DENIED")
} 
// ACCESS DENIED
```
## Logical AND Operator
논리 곱 연산자(Logical AND Operator,`a && b`)는 두 값 "모두" `true`이면 `true`이고, 하나라도 `false`이면 `false`가 됩니다. 첫번째에서 `false`이면 그 두번째 값부터는 평가하지 않는 **단락-회로 계산(short-circuit evaluation)**이 있습니다.

```swift
let  enteredDoorCode = true
let passedRetinaScan = false
if enteredDoorCode && passedRetinaScan {
	print("Welcome!")
} else {
	print("ACCESS DENIED")
} 
// ACCESS DENIED
```

## Logical OR Operator
논리 합 연산자(Logical OR Operator,`a || b`)는 두 값중 하나만 `true`이면`true`가 됩니다. 논리 곱 연산자와 마찬가지로 **단락-회로 계산**을 사용합니다.

```swift
let hasDoorKey = false
let knowsOverridePassword = true
if hasDoorKey || KnowsOverridePassword { 
	print("Welcome!")
} else {
	print("ACCESS DENIED")
} 
// "Welcome!"
```
## Combining Logical Operators
두 개 이상의 논리 연산자를 조합하여 복합(Compound) 표현식을 생성할 수 있습니다.

```swift
if enteredDoorCode && passedRetinaScan || hasDoorKey || knowsOverridePassword {
	print("Welcome")
} else {
	print("ACCESS DENIED")
}
// Prints "Welcome!"
```
> 스위프트의 논리 연산자 && 와 || 는 왼쪽의 표현을 우선해서 논리 계산을 합니다.

## Explicit Parentheses
명시적인 괄호(Explicit Parentheses)는 복잡한 표현식을 쉽게 이해하도록 괄호를 사용해 계산 순서를 지정할 수 있습니다.

```swift
if (enteredDoorCode && passedRetinaScan) || hasDoorKey || KnowsOverridePassword { 
	print("Welcome!")
} else {
	print("ACCESS DENIED")
}
// "Welcome!"
```
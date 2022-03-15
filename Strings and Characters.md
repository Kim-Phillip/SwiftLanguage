> [The Swift Language Guide](https://jusung.gitbook.io/the-swift-language-guide/language-guide/02-basic-operators)를 참조하여 공부한 내용을 정리했습니다.
>> <span style="color:black">Contents
>> 1. [Strings and Characters](#Strings-and-Characters)<br>
>> 

# Strings and Characters

스위프트 문자열에서는 `String` 타입으로 표현하고, 문자열(String)은 `"hello world"`같은 연속된 문자들을 말합니다.
문자열(String)의 내용물(Contents)은 문자(Character)값의 집합체(Collection)로 접근할 수 있습니다.
스위프트의 문자열과 문자타입은 `Unicode-Compliant`방식을 제공합니다.

> 스위프트 `String`타입은 `Foundation` 프레임워크의 `NSString`가 연동된 타입이기 때문에 `NSString`의 메소드를 `String`에서 캐스팅 없이 사용 가능합니다.
1) `Foundation` [1] 은 모든 스위프트 프로그래밍에서 사용하는 기본 프레임워크입니다. 

[1] : https://developer.apple.com/documentation/foundation
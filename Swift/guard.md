# guard


<br><br>
함수나 메서드, 반복문 등 블록 내부에 선언한다.

함수의 조건을 검사하는 용도로도 많이 사용 !

<br><br><br>

```swift
guard 조건 else {
	//조건이 false면 실행
    return || throw
}
  //조건이 true면 실행
```

guard문은 조건이 거짓일 때 내부 구문을 실행시키는 것이다. (조건문이 **true일 때를 더 강조**)

<br>

`if문 - 만약 ~이면 ~해라`   `guard문 - ~가 아니면 끝내라`

라는 의미이기 때문에 **빠른 종료**라는 장점이 있다.

<br><br><br>

---

<br><br><br>

```swift
func test() {
		let a: Bool = true
		let b: Bool = true

		guard a, b else {
			return 1
		}
}
```

위 코드에서 a 와 b 모두 true 이므로 조건이 참이되어 내부 구문을 실행시키지 않는다.

<br>
<aside>
🚨 guard문은 조건이 맞지 않을 경우 종료시키는 문법을 포함해야한다.
때문에 반드시 return이나 throw를 해준다.

</aside>

<br><br>

---

<br><br>

## guard와 if의 차이점
<br>

- guard구문은 함수나 메서드, 반복문 안에서만 사용할 수 있다는 한계점이 있다.
- guard구문은 else문을 생략할 수 없다.
  
  <br>

## guard문을 사용하는 이유
<br>

- 가독성 좋은 코드를 작성할 수 있다
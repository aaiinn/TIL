# map

<br>

데이터를 변형하고자 할 때 사용

기존의 컨테이너의 요소에 대해 정의한 클로저로 매핑한 결과를 새로운 컨테이너로 반환

(기존데이터는 변형되지 않음)

<br><br>

## 사용

<br>

String 배열 → Int 배열

```swift
let string = ["1", "2", "3", "4", "5"]
let numbers = string.map { Int($0)! }

print(numbers)
// [1, 2, 3, 4, 5]
```

<br>
numbers의 각 요소에 2 곱하기

```swift
let numbers = [1,3,5,7,9]
let multiArray = numbers.map { $0 * 2 }
print(multiArray)

// [2, 6, 10, 14, 18]
```
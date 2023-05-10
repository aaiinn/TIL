# filter

<br><br>

기존 컨테이너에서 **내부의 값들을 걸러서 추출**한다.

map과 마찬가지로 새로운 컨테이너에 걸러진 값들을 담아 반환하게 된다.

<br>

map은 기존의 요소를 변경한 값을 반환했다면 필터는 기준을 가지고 기준에 맞는 값들을 반환해 준다는 것 

<br><br>

---

<br><br>

## for-in

```swift
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
var evenNumbers: [Int] = []

for number in numbers {
    if number % 2 == 0 {
        evenNumbers.append(number)
    }
}

print(evenNumbers)
// [2, 4, 6, 8]
```

<br>

## filter

```swift
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
let evenNumbers = numbers.filter { $0 % 2 == 0 }

print(evenNumbers)
// [2, 4, 6, 8]
```

<br><br>

위와 같이 fiter를 사용했을 때 코드가 훨씬 간결해진 것을 볼 수 있다 !
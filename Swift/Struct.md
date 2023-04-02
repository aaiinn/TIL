# 구조체 (Struct)

<br><br>

인스턴스의 값(프로퍼티)을 저장하거나 기능(메소드)을 제공하고 

이를 캡슐화할 수 있는 스위프트가 제공하는 타입(named type)

<br>


```swift
struct Name {
    var name = "ain"                // 구조체 안의 변수 : 속성(property)
    
    func my_name() {
        print("my name is \(name)") // 구조체 안의 함수 : 메소드(method)
    }
}
```

```swift
var people : Name = Name()

print(people.name)
people.my_name()

people.name = "shinain"
people.my_name()
```

클래스와 구조체는 선언과 사용법이 비슷

<br><br>

---

<br><br>

## 구조체 사용법

<br><br>

```swift

struct 구조체 이름 { 
    프로퍼티와 메서드들
}

struct character {
    var name: String
    var isfavorite: Bool
    
}
 
var myCharacter: character = character(name: "포뇨", isfavorite: true)
myCharacter.name = "소피아"
myCharacter.isfavorite = false
 
print(myCharacter)  //character(name: "소피아", isfavorite: false)

```

<br>

```swift
struct Name {
    var name: String
    
    func my_name() {
        print("my name is \(name)")
    }
}

var people : Name = Name(name: "ain")

print(people.name)
people.my_name()
```

name속성의 값을 선언하지 않고 인스턴스 선언시 매개변수로 넣어줌

<br>

클래스는 내부에 init()메소드를 생성해야 했지만

구조체는에서는 자동으로 초기화 코드를 만들어준다.

초기화 코드를 직접 정의하면 자동 초기화 코드는 제공받지 못한다

<br><br>

---

<br><br>

## 구조체의 상속

구조체는 상속을 할 수 없다.

<br><br>

---

<br><br>

## 구조체를 사용하는 경우

<br>

• 연관된 몇몇의 값들을 모아서 하나의 데이터 타입으로 표현하고 싶을 때

• 다른 객체 또는 함수 등으로 전달될 때 **참조가 아닌 복사를 원할 때**

• 자신을 상속할 필요가 없거나 자신이 다른 타입을 **상속받을 필요가 없을 때**
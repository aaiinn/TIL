# Class

<br><br>

Swift에서는 클래스를 정의하여 객체를 만들고 사용할 수 있다

<br>

```swift
class Name {
    var name = "ain"                   // 클래스 안의 변수 : 속성(property)
    
    func my_name() {
        print("my name is \(name)")    // 클래스 안의 함수 : 메소드(method)
    }
}
```
클래스를 선언하기 위해서는  class 클래스 이름 { '코드' } 를 작성해준다.

<br><br>


```swift
let people : Name = Name()
```
선언한 클래스를 사용할 수 있도록 **인스턴스**를 만들어준다.

상수 people은 Name이라는 클래스 데이터 타입을 가지게 되는 것

<br><br>

```swift
print(people.name)
people.my_name()           // my name is ain

people.name = "ShinAin"
people.my_name()           // my name is ShinAin
```
클래스의 속성이나 메소드에 접근할 때는 . 사용

<br><br>

---

<br><br>

# 클래스 상속 (Inheritance)

<br><br>

기존 클래스이 기능을 받아 새로운 클래스를 정의하는 것

편리한 클래스를 상속받아 자신의 기능을 추가하여 사용 가능

<br><br>

```swift
class Name {
    var name = "ain"                   // 클래스 안의 변수 : 속성(property)
    
    func my_name() {
        print("my name is \(name)")    // 클래스 안의 함수 : 메소드(method)
    }
}

```

슈퍼클래스

<br><br>

```swift
class YourName : Name {  //클래스 상속!!
    var yourName = "yunseo"
    
    func ourName() {
        print("my name is \(name) and your name is \(yourName)")
    }
}
```

슈퍼클래스를 상속받은 클래스

<br><br>


```swift
let people : YourName = YourName()

print(people.name)     //"ain" 출력
print(people.yourName) //"yunseo" 출력

people.my_name() //클래스 상속으로 my_name()메소드 사용 가능
people.ourName()
```

YourName클래스 안에서 Name클래스의 변수와 함수를 이용할 수 있다

YourName클래스에는 name변수가 없지만 ourName메소드에서 name변수를 사용하는 것

<br><br>

---

<br><br>

# 클래스 초기화 (Initialization)
<br><br>

여러 인스턴스를 만들고 원하는 인수를 지정해줄 수 있는 것

인스턴스를 만들 때 **자동으로 호출되는 초기화 처리 전용의 메소드**

<br><br>

```swift
class Name {
    var name : String
    var age : Int
    
    init(name:String, age:Int) {   // 초기화
        self.name = name
        self.age = age
    }
    
    func my_name() {
        print("my name is \(name) and \(age) year's old")
    }
}
```

클래스안 속성들에게 값을 지정해 주지 않고 **init()** 메소드를 이용하여 초기화

init 메소드 안의 **self** 는 자기 자신을 가르키는 값

<br><br>


```swift
let people1 : Name = Name(name: "ain", age: 18)
let people2 : Name = Name(name: "jumee", age: 18)

people1.my_name()    // my name is ain and 18 year's old
people2.my_name()    // my name is jumee and 18 year's old
```

name과 age 변수를 각각 지정해 준 뒤 인스턴스를 생성해보면 인수들을 지정해 줄 수 있다.

<br><br>


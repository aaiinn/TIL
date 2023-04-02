# Optional

<br><br>

## Optional 이란?

<br>
값이 있거나 없을 수도 있는 Enum형(열거형)타입

옵셔널로 선언된 변수에만 nil 할당 가능

**nil을 사용할 수 있는 타입과 없는 타입을 구분하기 위함**

<br><br>

---

<br><br>


## Optional의 선언

<br>

 `?`  키워드 사용

`Oprional<Int>`  사용

<br>

```swift
var name: String? // 자료형 뒤에 ?를 붙여준다
name = nil

var num: Optional<Int>
```

옵셔널에서만 nil 사용 가능

<br><br>

---

<br><br>

## Optional 추출

<br><br>

옵셔널 안에 있는 값을 원하는 대로 사용하기 위해 값을 둘러싼 옵셔널 객체를 해제

객체를 해제하고 값을 추출하는 과정을 **옵셔널 언래핑**이라고 함

<br><br>

- 암시적 추출 옵셔널 (Implicitly UnWrapped Optional )
    
    <br>
    옵셔널을 정의할 때 타입 뒤에 물음표 대신 느낌표를 붙여줌
    
    암시적 추출 옵셔널로 지정된 타입은 일반 값처럼 사용할 수 있으나
    
    nil도 할당해줄 수 있다 nil이 할당되어 있을 때 접근을 시도하면 오류 발생
    
    ```swift
    var str: String! = "ain"
    print(str)
    
    //ain
    ```
    
    변수가 nil이 될 가능성이 있다면 사용 X
    
    클래스와 구조체 안에서 자주 사용


<br><br><br>

    
- 옵셔널 강제 추출(Forced UnWrapping)
    
    <br>
    옵셔널 타입의 값 뒤에  `!`  기호 붙이기
    
    ! = 강제 추출 연산자 (Forced-UnWrapping Operator)
    
    ```swift
    var optInt: Int? = 2
    print("옵셔널 추출 하기 전의 값: \(optInt)")
    print("옵셔널 추출 후의 값: \(optInt!)") //강제 추출 연산자 사용
    
    //실행 결과
    옵셔널 추출 하기 전의 값: Optional(2)
    옵셔널 추출 후의 값: 2
    ```
    
    ```swift
    var name: String? = "ain"
    var myName: String = name!
    ```
    
    ```swift
    name = nil
    myName = name! // 런타임 오류
    ```
    
    🚨  옵셔널 값이 nil일 때 오류 발생


<br><br><br>

    
- 옵셔널 바인딩(Optional Binding)
    
    <br>
    옵셔널 값이 존재하는지 검사한 뒤 그 값을 변수에 대입
    
    만약 옵셔널에 값이 있다면 추출한 값을 일정 블록 안에서 사용할 수 있는 
    
    상수나 변수로 할당해서 옵셔널이 아닌 형태로 사용할 수 있도록 해줌
    
    **if let**이나 **if var**를 사용 
    
    옵셔널에 값이 있다면 if문을 실행하고 nil이라면 빠져나온다
    
    ```swift
    var optionalEmail = "s22028@gmail.com"
    
    if let email = optionalEmail {
    		print(email) //optionalEmail값이 존재한다면 실행
    }
    //optionalEmail값이 존재하지 않는다면 if문을 지나침
    ```


<br><br><br>

    
- 옵셔널 체이닝(Optional Chaining)
    
    
    옵셔널에 값이 있다면 프로퍼티, 메서드, 서브스크립트 등을 호출할 수 있고
    
    옵셔널이 nil이라면 nil을 반환
    
    이러한 옵셔널을 반복 사용하여 체인처럼 서로 꼬리를 물고 있는 모양을 옵셔널 체이닝이라고 함
    
    호출하고 싶은 옵셔널 변수나 상수 뒤에 **물음표(?)** 를 붙여 표현
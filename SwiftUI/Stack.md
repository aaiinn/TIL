# Stack

<br><br>

**한 개 이상의 View를 묶어서 배치할 때 사용할 수 있는 것**

<br>

SwiftUI 뷰를 생성할 때, 뷰의 body 프로퍼티에는 content, layout 및 동작을 기술한다

하지만 이 body 프로퍼티는 오직 하나의 싱글 뷰만 반환하는데

스택을 사용하면 이 뷰들을 결합시키고 임베드할 수 있다.

<br><br>

## 1. HStack

Horizontal Stack 수평 스택을 의미

**내부에 선언된 View들을 Leading에서 Trailing으로 배치한다**

HStack은 자식들의 크기만큼 늘어나게 되며 기본값으로 정중앙에 위치하게 된다.

<br><br>

## 2. VStack

Vertical Stack 수직 스택을 의미

**내부에 선언된 View들을 Top에서 Bottom으로 배치한다**

HStack과 유사하게 텍스트가 중앙으로 정렬된다

<br><br>

### 3. ZStack

Z축을 기준으로 뷰를 쌓는 스택

**내부에 선언된 View들을 겹쳐서 두 축으로 배치한다**

뷰를 겹쳐서 표현할때 사용

<br>

```Swift
var body: some View {
        ZStack{
            Color.yellow.edgesIgnoringSafeArea(.all)
            Color.red.frame(width:300,height: 300)
            Color.blue.frame(width:200,height: 200)
        }
    }
```
![ZStack결과](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*oTEg_LROcRzJk2djC-O-6Q.png)

<br><br>

---

<br><br>

## modifer

<br>

### ****Stack의 크기 변경하기****

**Stack의 크기는 내부 뷰를 표시하기 위한 최소한의 크기로 표시된다**

Stack의 Frame을 직접 지정해주고 싶을 경우 `.frame` 이라는 modifier를 이용해서 직접 설정

```swift
.frame(width:200,height: 200)
```

<br><br>
 

### ****Stack 내의 정렬 방식(alignment) 변경하기****

**Stack들은 기본 정렬이 .center**이기 때문에 

Text의 너비에 의해 스택의 너비가 결정되어나머지 Text들이 모두 가운데 정렬 ****되어버린다

**Stack을 생성할 때 파라미터 값으로 alignment를 직접 설정**

```swift
VStack(alignment: .trailing)
VStack(alignment: .leading)
VStack(alignment: .center)
```

<br><br>

### ****Stack 내의 여백(spacing) 크기 변경하기****

**Stack 내부 뷰 간격 간의 여백을 지정하는 spacing이란 파라미터의 기본 값은 nil인데 이때 nil은 0이 아니라 기본 값이다**

만약 여백을 직접 설정하고 싶거나, 아예 없애고 싶다면 정렬과 마찬가지로

**Stack을 생성할 때 파라미터 값으로 spacing을 설정**

```swift
HStack(spacing: 0) //여백 없앰
```

<br><br>

### **뷰를 맨 위와 맨 끝에 정렬하게 하려면?**

```swift
var body: some View {
        VStack(alignment: .leading, spacing: 20){
           Text("hello world!")
           Spacer()
           Text("he")
       }
    }
```

![Spacer](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*cHyf7PKF-6cfytysE4skJQ.png)

Spacer를 선언하면 별도의 옵션을 주지 않는 이상 가능한 모든 영역을 차지하게 되고 

부모 뷰인 VStack 역시 Spacer로 인해 가능한 모든 영역만큼 크기가 늘어난다.

<br>


```swift
Spacer().frame(height:5)
```

별도의 frame값을 주게되면 선언한 width 혹은 height값만큼만 공간을 차지한다.
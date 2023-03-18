# Tutorial

<br>

[SwiftUI 란?](../iOS%20Framework/SwiftUI.md)


<br><br><br>

SwiftUI로 프로젝트를 생성하면 프로젝트명App , ContentView 파일이 있다.

<br><br>
ex)프로젝트명이 SettingApp일 때

SettingAppApp.swift

<br>

<pre>
<code>
import SwiftUI

@main
struct SettingAppApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
</code>
</pre>

첫번째 파일에서는 SettingAppApp구조체가 App 프로토콜을 채택하고 있는 것을 볼 수 있다

SwiftUI 앱 라이프 사이클을 사용하는 앱은 App 프로토콜을 준수해야 한다.

SwiftUI에서 View는 반드시 body 변수가 있어야하며 최상위 View 역할을한다.

body 프로퍼티는 하나 이상의 scene을 반환한다

@main은 앱의 진입점을 가리키는 attribute identifier이다

<br><br>


ContentView.swift
<pre>
<code>
import SwiftUI

struct ContentView: View {
    var body: some View {
        Text("Hello, world!")
            .padding()
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
</code>
</pre>
기본적으로 SwiftUI 뷰 파일은 두 가지 구조체를 선언한다.

첫 번째 구조체는 View 프로토콜을 준수하며 뷰의 컨텐츠와 레이아웃 묘사

View는 반드시 body 변수가 있어야하며 최상위 View 역할을 한다

두 번째 구조체는 해당 뷰에 대한 Preview 선언

<br><br>

---

<br><br>

<pre>
<code>
struct ContentView: View {
    var body: some View {
        Text("Hello")
            .font(.body) // modifier
            .fontWeight(.medium) // modifier
            .foregroundColor(.green) // modifier
    }
}
</code>
</pre>
SwiftUI View를 커스터마이즈 하기 위해서는 modifiers라는 메서드를 호출해야한다

modifiers는 뷰를 랩핑하여 디스플레이나 다른 속성들을 변경한다

modifiers는 새로운 View를 반환하므로 여러 modifier를 수직으로 쌓듯이 연결하는 것이 일반적

<br><br>

---

<br><br>

<pre>
<code>
var body: some View {

	Form{
	
	Text("Hello World")

	Group{
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	}
 
  Group{
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")
	   Text("Hello World")}
	}
}
</code>
</pre>
Swift UI에서 최상위 View는 최대 10개의 Child View를 가질 수 있고 

만약 10개를 초과하게 된다면 다른 태그를 이용하여 감싸주어야한다
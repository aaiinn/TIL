# UIkit

<br><br><br>

## UIkit 란?
<br>

`UI(User Interface)` 라는 이름에서 알 수 있듯이 

사용자의 인터페이스를 관리하고, 이벤트를 처리하는 프레임워크

<br>

iOS 이전의 macOS 에서는 비슷한 개념으로

`Appkit` 이라는 프레임워크를 사용했었지만

iOS로 넘어오면서 비슷한 개념을 가진 `UIkit` 으로 대체

<br><br><br>

* 제스처 처리, 애니메이션, 그림 그리기, 이미지 처리, 텍스트 처리 등 사용자 이벤트 처리를 위한 클래스를 포함
* 테이블뷰, 슬라이더, 버튼, 텍스트 필드, 얼럿 창 등 애플리케이션 화면을 구성하는 요소들을 포함
* Responder에서 파생된 클래스나 사용자 인터페이스에 관련된 클래스는 애플리케이션의 메인 스레드(혹은 메인 디스패치 큐)에서만 사용
* UIKit은 iOS와 tbOS플랫폼에서 사용
* UIKit을 import하면 Foundation은 자동으로 import된다.


<br><br><br>

---

<br><br>

## UIkit 기능별 요소

<br><br><br>

**사용자 인터페이스**

<br>

* View and Control : 화면에 컨텐츠 표시
* View Controller : UI 관리
* View Layout : 스택 뷰를 사용해 인터페이스를 나타냄
* Appearance Customization : 다크 모드, bar 커스터마이징 등
* Animation and Haptics : 애니메이션과 햅틱을 통한 피드백 제공
* Window and Screen : 뷰 계층을 위한 윈도우 제공

<br><br><br>

**사용자 인터페이스**

<br>

* Touch, Press, Gesture: 제스처 인식기를 통한 이벤트 처리 로직
* Drag and Drop: 화면 위에서 드래그 앤 드롭 기능
* Peek and Pop: 3D 터치에 대응한 미리 보기 기능
* Keyboard and Menu: 키보드 입력을 처리 및 사용자 정의 메뉴 표시

<br><br><br>

---

<br><br><br>

# UIKit 계층도

<br><br>

![UIkit계층도](https://velog.velcdn.com/images/jamong-i/post/69e4b486-08be-4174-9ef5-281482cb29be/image.png)
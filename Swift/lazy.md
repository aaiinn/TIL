# lazy

<br><br><br>

**처음 사용되기 전까지 초기값이 계산되지 않는 프로퍼티**

생성자에서 초기화 하지 않기 때문에 선언 시점에 **기본값**을 저장해주어야 한다.

<br>

<aside>

    🚨  lazy는 struct와 class에서만 사용할 수 있다
        lazy는 반드시 **var** 키워드를 사용해 변수로 선언해야 한다.
        초기 값은 인스턴스 초기화가 완료 될 때까지 검색되지 않을 수 있기 때문

</aside>

<br><br>

---

<br><br>

```swift
class DataImporter {
    var filename = "data.txt"
}

class DataManager {
    lazy var importer = DataImporter()
    var data = [String]()
}

let manager = DataManager()
manager.data.append("Some data")
manager.data.append("Some more data")
```

위 코드에서 importer 변수가 lazy로 선언되었기 때문에 

**importer 변수는 사용되기 전까지 DataImporter 인스턴스가 생성되지 않고 메모리에 올라가지 않는다.**

<br>

즉, 지금은 DataManager의 data 변수만 사용되었으므로 DataImporter가 초기화되지 않은 것.

importer 프로퍼티가 **처음 사용될 때 DataImporter 인스턴스가 생성되고 메모리에 올라간다.**

<br><br>

---

<br><br>

## lazy를 사용하는 이유

<br>

- 메모리를 효율적으로 관리할 수 있다.
    
    복잡한 앱일수록 모든 인스턴스를 메모리에 올리면 과부하로 앱이 종료될 위험이 있다
    
    하지만 각 인스턴스들이 사용되는 시점에 생성하면 메모리 관리에 효율적이다.
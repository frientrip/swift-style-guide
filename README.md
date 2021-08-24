# Frip Swift Style Guide
프렌트립 iOS 개발자들이 코드를 이해하고 작성하는데, 조금 더 도움을 주고 명확하게 의사소통하기 위한 스위프트 스타일 가이드입니다.  
아래 내용들을 바탕으로 코드 리뷰 때, 신명나게 지적해주세요.😜
해당 내용들 중 반영하고 싶은 내용이나 수정하고 싶은 내용이 있다면 언제든 PR날려주세요!
더 원활한 코딩을 위한 개선은 언제든 환영이라구요!

## 목차
- [네이밍](#네이밍)
  - [디랙토리](#디렉토리)
  - [파일명](#파일명)
  - [클래스](#클래스)
  - [함수](#함수)
  - [변수](#변수)
  - [상수](#상수)
  - [enum](#enum)
  - [약어](#약어)
- [포맷팅](#포맷팅)
  - [최대 줄길이](#최대-줄길이)
  - [들여쓰기](#들여쓰기)
  - [띄어쓰기](#띄어쓰기)
  - [줄바꿈](#줄바꿈)
- [클래스와 구조체](#클래스와-구조체)
- [클로저](#클로저)
- [뷰](#뷰)
- [뷰컨트롤러](#뷰컨트롤러)
- [Reference](#reference)
- [License](#license)

## 네이밍
### 디렉토리
- 디렉토리 이름은 대문자로 시작하는 단어로 설정합니다.
- 해당 디렉토리에 비슷한 기능을 하는 파일들이 들어있다면 단어의 끝에 복수로 `s`를 붙여줍니다.
    - **Good👏**
         ```swift
         - Domains, Analytics, Managers...
         ```
    - **Bad👎**
        ```swift
        - Model(X), Service(X)...   => Models, Services
        ```

### 파일명
- 파일명은 `UpperCamelCase`를 사용합니다.
- 뷰 컨트롤러는 줄여서 쓰지 않고 `ViewController`로 사용합니다.
- 뷰모델 혹은 리액터는 뷰 컨트롤러와 매칭되는 **접두사(prefix)**를 사용합니다.
  - **Good👏**
    ```swif
    - HomeReactor.swfit
    - HomeViewController.swift
    ```
  - **Bad👎**
    ```swift
    - HomeViewReactor.swfit
    - HomeVC.swfit
    ```

### 클래스
- 클래스 이름은 `UpperCamelCase`를 사용합니다.

### 함수
- 함수 이름은 `lowerCammerCase`를 사용합니다.
- 함수 이름에 `get`이란 단어는 최대한 지양합니다.
	- get이란 단어는 광범위 하므로 다른 개발자가 읽었을 때 한번에 이해할 수 있을 만한 함수의 액션을 나타내는 단어를 사용합니다.
  - **Good👏**
    ```swift
    func fetchUserInfo() {
    ...
    }
    
    func searchUser() {
    ... 
    }
    ```
  -  **Bad👎**
        ```swift
        func getUserInfo() {
        ...
        }
     ```

### 변수
- 변수 이름은 `lowerCammerCase`를 사용합니다.
- 변수 타입 중 Bool타입은 is 와같은 be동사를 접두사를 붙여서 사용합니다.
- 배열 혹은 리스트와 같이 복수의 의미를 담고있는 변수라면 끝에 **s**를 붙여서 사용합니다.
  - **Good👏**
    ```swift
    var messages: [String]
    var userInfo: UserInfo
    var isFinished: Bool
    ```
  - **Bad👎**
    ```swift
    var message: [String]
    var finished: Bool
    ```

### 상수
- 상수 이름은 `lowerCammerCase`를 사용합니다.
  -  **Good👏**
        ```swift
        let profileImageWidth = 100
        ```
    
  - **Bad👎**
    ```swift
    let PROFILE_IMAGE_WIDTH = 100
    ```

### enum
- 열거형 enum 변수들은 `lowerCammerCase`를 사용합니다.
  - **Good👏**
    ```swift
    enum ContentType {
      case text
      case image
    }
    ```

  - **Bad👎**
    ```swift
    enum ContentType {
      case Text
      case IMAGE
    }
    ```

### 약어
- 약어로 시작하는 경우에는 소문자를 사용합니다.
- 중간에 약어가 들어가는 경우에는 대문자를 사용합니다.
  - **Good👏**
    ```swift
    var userID: String
    var html: String
    var imageURL: String
    ```

  - **Bad👎**
    ```swift
    var userId: String
    var HTML: String
    var imageUrl: String
    ```

## 포맷팅
### 최대 줄길이
- 한줄 최대 길이는 **100**자로 설정합니다.
- XCode > Preferences > Text Editing > Display > Page guide at column에서 설정 가능합니다.
![image](uploads/ab992d3b18029f4752d8fa65e1bcb7fc/image.png)

### 들여쓰기
- 들여쓰기는 4 spaces로 설정합니다.
- XCode > Preferences > Text Editing > Indentation에서 설정 가능합니다.
![image](uploads/20d18c9a1e7ba218c3dbff7e38f441bc/image.png)

### 띄어쓰기
- 콜론(:)뒤에는 띄어쓰기를 사용합니다.
  - **Good👏**
    ```swift
    var userID: String
    ```

  - **Bad👎**
    ```swift
    var userID : String
    ```

- 삼항 연산자의 경우에는 콜론(:) 앞에도 띄어쓰기를 사용합니다.
  - **Good👏**
    ```swift
    likeCount = isLiked ? 0 : 1
    ```

  - **Bad👎**
    ```swift
    likeCount = isLiked ? 0: 1
    ```

- 함수를 정의할 때, 인자 콤마(,)뒤에는 띄어쓰기를 사용합니다.
  - **Good👏**
    ```swift
    func sum(number1: Int, number2: Int)
    ```

  - **Bad👎**
    ```swift
    func sum(number1: Int,number2: Int)
    ```

- 연산자 앞뒤로 공백을 추가해서 사용합니다.
  - **Good👏**
    ```swift
    var sum = 20 + (40 / 2)
    ```

  - **Bad👎**
    ```swift
    var sum = 20+(40/2)
    ```

### 줄바꿈
- 함수의 인자 혹은 이름이 길어서 100자 이상길어질 경우 다음과 같이 줄바꿈 합니다.
  - **Good👏**
    ```swift
    self.navigationController.pushViewController(
      viewController, 
      animated: true
    )
    ```

  - **Bad👎**
    ```swift
    self.navigationController.pushViewController(viewController, animated: true)
    ```

- 배열의 컨텐츠를 정의할 때 길이가 길어진다면 다음과 같이 줄바꿈 합니다.
  - **Good👏**
    ```swift
    self.addSubViews([
      self.titleLabel,
      self.titleButton,
      self.nextButton
    ])
    ```

  - **Bad👎**
    ```swift
    self.addSubViews([self.titleLabel, self.titleButton,
      self.nextButton])
    ```

- 변수의 네이밍과 타입명이 길어서 정의하는데 100줄이 넘어간다면 다음과 같이 줄바꿈 합니다.
  - **Good👏**
    ```swift
    private var myPageTableViewDataSource = 
      RxTableViewSectionedReloadDataSource<MyPageSecionModel>()
    ```

  - **Bad👎**
    ```swift
    private var myPageTableViewDataSource = RxTableViewSectionedReloadDataSource<MyPageSecionModel>()
    ```

- if let 구문이 길어질 경우에는 쉼표 이후에 줄바꿈을 합니다.
  - **Good👏**
    ```swift
    if let myInfo = self.userInfo,
      let myAge = myInfo.age,
      let myNickname = myInfo.nickname {
        ..
      }
    ```

  - **Bad👎**
    ```swift
    if let myInfo = self.userInfo, let myAge = myInfo.age, let myNickname = myInfo.nickname {
      ..
    }
    ```
- guard let ... else 는 한줄에 표시합니다.
  - **Good👏**
    ```swift
    guard let myInfo = self.userInfo else { return }
    ```

  - **Bad👎**
    ```swift
    guard let myInfo = self.userInfo 
    else {
      return
    }
    ```

- switch문 안의 case문은 줄바 꿈 후 내용을 정의합니다.
- case문들 사이에는 한줄 공백을 추가합니다.
  - **Good👏**
    ```swift
    switch action {
      case .tapHome:
        print("Tap home")
      
      case .tapRefresh:
        print("Tap refresh")
    }
    ```

  - **Bad👎**
    ```swift
    switch action {
      case .tapHome: print("Tap home")
      case .tapRefresh: print("Tap refresh")
    ```

## 클래스와 구조체
- 클래스, 구조체 지역 변수를 사용할 때, `self`를 명시적으로 사용합니다.
- 더이상 상속이 이루어지지 않는 클래스에는 `final` 키워드를 붙입니다.
- 프로토콜을 채택할 경우, `extension`을 사용합니다.
  - **Good👏**
    ```swift
    class ViewController: UIViewController {
    ...
    }
     
    extension ViewController: UITableViewDelegate {
    ...
    }
    ```

  - **Bad👎**
    ```swift
    class ViewController: UIViewController, UITableViewDelegate {
    ...
    }
    ```


## 클로저
- 클로저 내의 인자에는 괄호를 사용하지 않습니다.
  - **Good👏**
    ```swift
    asyncFunction() { argument1, argument2 in
      ...
    }
    ```

  - **Bad👎**
    ```swift
    asyncFunction() { (argument1, argument2 in
      ...
    }
    ```
- 사용하지 않는 클로저 인자는 `_`로 선언합니다.
  - **Good👏**
    ```swift
    asyncFunction() { _, argument2 in
      print(argument2)
    }
    ```

  - **Bad👎**
    ```swift
    asyncFunction() { argument1, argument2 in
      print(argument2)
    }
    ```

## 뷰
- UI 컴포넌트 정의 사이에는 한줄 공백을 추가합니다.
  - **Good👏**
    ```swift
    // MainView.swift
    let titleLabel = UILabel()
     
    let titleButton = UIButton()
    ```

  - **Bad👎**
    ```swift
    // MainView.swift
    let titleLabel = UILabel()
    let titleButton = UIButton()
    ```
- UIView 상속 클래스들의 변수 및 함수 선언 순서는 다음과 같습니다.
  - 상수
  - UI컴포넌트 정의
  - 생성자 및 소멸자
  - override 함수
  - public 함수
  - private 함수
- 같은 접근 제어자를 가진 함수 내에서는 사용 순서대로 선언합니다.

## 뷰컨트롤러
- ViewController를 상속하는 클래스들의 변수 및 함수 선언 순서는 다음과 같습니다.
  - 상수
  - View, ViewModel 변수 정의
  -  생성자 및 소멸자
  - override 함수 (ViewController lifecycle)
  - public 함수
  - private 함수

## Reference
- [Google Swift Style Guide](https://google.github.io/swift/)
- [Airbnb Swift Style Guide](https://github.com/airbnb/swift)
- [StyleShare Swift Style Guide](https://github.com/StyleShare/swift-style-guide#%EC%B5%9C%EB%8C%80-%EC%A4%84-%EA%B8%B8%EC%9D%B4)

## License
본 문서의 저작권은 [유현식](https://github.com/Hyunsik-Yoo)과 [프립](https://www.frip.co.kr/)에게 있습니다.

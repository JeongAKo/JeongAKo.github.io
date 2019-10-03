---
layout: post
title:  "Welcome to Jekyll!"
date:   2019-10-02 21:15:32
categories: git
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

## 골치아픈 이름 짓기

프로그래머들에게 가장 어려운 것 하나만 꼽아보라고 하면 절반이 `naming`을 선택한다고 합니니다. 프로그램을 작성하면서 파일명, 클래스명, 변수명, 함수명 등 수도 없이 많은 이름들을 지어내야 합니다. 거의 작명소 수준입니다. 그런 이름 짓기보다 더 어려운 것이 있습니다. 바로 `커밋 메시지` 작성입니다.

한글로 커밋 메시지를 작성하는 팀이라면 별 걱정이 없겠으나, 영문으로 작성하는 팀이라면 만만치 않은 일입니다. 하고 싶은 말은 많은데, 막상 쓰지를 못하니 이렇게 답답할 수가 없습니다. 최근 커밋 메시지 하나를 올리며 이런 저런 생각들이 들었습니다. 이게 문법에 맞는걸까, 왜 자꾸 문장이 길어지는걸까, 말인지 방구인지 알고 쓰고 있는걸까. 그래서 차라리 영어권 프로젝트에서 어떤 식으로 작성하는지 살펴보고 패턴을 분석해보기로 했습니다.

어떻게 메시지가 간결해질 수 있는지, 또 알아두면 좋을 특징들이 있는지 살펴봅시다.



## 커밋 메시지 규칙

이미 유정하지만, 커밋 메시지를 작성하는 좋은 규칙들을 공유합니다.

- [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
- [AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit)

그 외에, 이번 분석을 통해 생각해 본 간결한 메시지를 위한 또다른 규칙들은 다음과 같습니다:

#### 동명사보다 명사를 사용합니다.

동사를 명사화시키기 보다는 그 의미를 잘 표현하는 명사를 찾아서 사용합니다. 이렇게하면 문장이 장황하지 않고 간결해집니다. 아무래도 영어에 약한 사람들에게 가장 어려운 미션 중 하나가 아닐까 생각됩니다.

#### 관사는 사용하지 않습니다.

꼭 필요한 경우가 아니면 **a**, **an**, **the**는 사용하지 않습니다.

#### 부정문 `Don't`를 사용합니다.

커밋 메시지를 명령문 형태로 써야 한다는 것은 모두들 알고 있지만, 부정 명령문을 사용하는 것은 잘 모릅니다. ‘A를 사용해’라고 명령했으니 반대를 이야기 할 때는 ‘A를 사용하지마’로 표현해야 합니다. Not use가 아니라 Don’t use 입니다.

#### 오타 수정은 Correct misspelled text가 아닙니다.

그냥 **Fix typo**라고만 하면 됩니다.



## 좋은 커밋 메시지를 위한 영어 단어 목록

node.js와 React 프로젝트의 Change History를 참고로 자주 반복되는 로그 메시지의 패턴을 정리해 봤습니다. 특별한 목적의 커밋이 아닌 이상 대부분의 메시지는 아래의 경우들에 포함 됩니다. 문장을 명료하게 만들어주는 문법들도 적어 보았습니다.

### FIX

가장 자주 사용되는 커밋 로그 중 하나로 ‘Fix’가 있습니다. 보통 올바르지 않은 동작을 고친 경우에 사용합니다.

#### Fix A

> A를 수정합니다

```swift
Fix stat cache
Fix changelog entry
Fix broken jsiexecutor search path.
```

#### Fix A in B

> B의 A를 수정합니다

가장 자주 사용되는 패턴입니다.

```swift
Fix calculation in process.uptime()
Fix build warning in node_report.cc
Fix error condition in Verify::VerifyFinal
Fix typo in callback.cc
Fix duplicate symbols linker error in xcodeproj
```

#### Fix A which B, Fix A that B

> B절인 A를 수정합니다

‘Fix A’로 끝낼 수 있지만, 보다 많은 정보를 주기 위해 which나 that 관계 대명사로 A를 설명합니다. 무엇을 수정한 것인지 보다 상세하게 설명할줄 때 주로 사용됩니다.

```swift
Fix incorrect type which makes animated gifs not loop forever on device
Fix crash that happens when a component throws an exception that contains a null message
```

#### Fix A to B, Fix A to be B

> B를 위해 A를 수정합니다

왜 수정하는지를 추가로 설명합니다.

```swift
Fix inability to remove 'Disabled' state from AccessibilityStates
Fix HTTP connection timeout callback to be appropriately called
```

#### Fix A so that B

> A를 수정해서 B가 되었습니다

‘Fix A to B’와 의미는 비슷하나, 어감이 살짝 다릅니다. 고쳐진 B의 상태가 보다 강조됩니다.

```swift
Fix react-native init --help so that it doesn't return undefined
Fix Android 28's inverted ScrollView so that momentum is in the proper direction
```

#### Fix A where B

> B처럼 발생하는 A를 수정했습니다

여기서 A는 보통 ‘issue’, ‘error’, ‘crash’등이 들어갑니다. B는 문제가 발생한 모습을 적어주면 됩니다.

```swift
Fix case where content of inline views didn't get relaid out
Fix case where inline view is visible even though it should have been truncated
Fix issue where Image.resizeMode isn't respected while source is loading, resulting in unexpected padding
```

#### Fix A when B

> B일 때 발생하는 A를 수정했습니다

여기서 A는 보통 ‘issue’, ‘error’, ‘crash’등이 들어갑니다. B는 문제가 발생하는 상황을 적어주면 됩니다.

```swift
Fix accidental showing of Modal when visible prop is undefined or null
Fix crash when removing root nodes
```

### ADD

코드나 테스트, 예제, 문서 등의 추가가 있을 때 사용합니다

#### Add A

> A를 추가합니다

추가하는 행위는 대부분 목표나 목적이 명시되기 때문에 이 패턴은 자주 사용되지 않습니다.

```swift
Add ERR_INSPECTOR_COMMAND error
```

#### Add A for B

> B를 위해 A를 추가했습니다

```swift
Add documentation for the defaultPort option
Add example for setting Vary: Accept-Encoding header in zlib.md
Add missing includes for vtune build
Add test for dynamically enabling node.async_hooks tracing
Add test for InterpolatorType
Add devDependencies support for templates
```

#### Add A to B

> B에 A를 추가했습니다

```swift
Add error description to Image onError callback
Add displayName to ActivityIndicator
Add deprecation notice to SwipeableListView
```

### REMOVE

코드의 삭제가 있을 때 사용합니다. ‘Clean’이나 ‘Eliminate’를 사용하기도 합니다. 보통 A 앞에 ‘unnecessary’, ‘useless’, ‘unneeded’, ‘unused’, ‘duplicated’가 붙는 경우가 많습니다.

#### Remove A

> A를 삭제합니다

```swift
Remove fallback cache
Remove unnecessary italics from child_process.md
Remove useless additionnal blur call
Remove unneeded .gitignore entries
Remove unused variable
Remove duplicated buffer negative allocation test
```

#### Remove A from B

> B에서 A를 삭제합니다

```swift
Remove absolute path parameter from transformers
Remove trailing slash from origin header if no port is specified
```

### USE

특별히 무언가를 사용해 구현을 하는 경우입니다.

#### Use A

> A를 사용합니다

‘사용하였음’을 이야기 할 때는 대체적으로 목적이 필요하기 때문에 이 용법은 자주 사용되지 않습니다.

```swift
Remove absolute path parameter from transformers
Remove trailing slash from origin header if no port is specified
```

#### Use A for B

> B에 A를 사용합니다

```

```

#### Use A to B

> B가 되도록 A를 사용합니다

```

```

#### Use A in B

> B에서 A를 사용합니다

```

```

#### Use A instead of B

> B 대신 A를 사용합니다

```

```

### REFACTOR

전면 수정이 있을 때 사용합니다.

#### Refactor A

```

```

### SIMPLIFY

복잡한 코드를 단순화 할 때 사용합니다. Refactor의 성격이 강하나 이보다는 약한 수정의 경우 이용하면 좋습니다.

#### Simplify A

> A를 단순화합니다

```

```

### UPDATE

개정이나 버전 업데이트가 있을 때 사용합니다. Fix와는 달리 Update는 잘못된 것을 바로잡는 것이 아니라는 점에 주의해야 합니다. 원래도 정상적으로 동작하고 있었지만, 수정, 추가, 보완을 한다는 개념입니다. 코드보다는 주로 문서나 리소스, 라이브러리등에 사용합니다.

#### Update A to B

> A를 B로 업데이트 합니다.

```

```

> A를 B하기 위해 업데이트 합니다

```

```

### IMPROVE

향상이 있을 때 사용합니다. 호환성, 테스트 커버리지, 성능, 검증 기능, 접근성 등 다양한 것들이 목적이 될 수 있습니다.

#### Improve A

> A를 향상시킵니다

```

```

### MAKE

주로 기존 동작의 변경을 명시합니다.

#### Make A B

> A를 B하게 만듭니다

- config object를 read-only로 만듭니다.
- floating patch 메시지에 더 많은 정보가 담기도록 만듭니다.
- ViewPropTypes의 값들을 옵셔널하게 만듭니다.
- read()를 유저가 원한다면 무기한으로 호출되도록 만듭니다.
- IsolateData가 ArrayBuffer를 저장하도록 만듭니다.

모두 기존의 동작을 바꾼 것들입니다. 새롭게 뭔가를 만들었을 때는 Make 대신, Add를 사용해야 합니다.

```

```

### IMPLEMENT

코드가 추가된 정도보다 더 주목할 만한 구현체를 완성시켰을 때 사용합니다.

#### Implement A

> A를 구현합니다

‘Add’에 비해 더 큰 단위의 코드 추가에 사용되며, 특히 모듈이나 클래스 등의 단위에 사용되기 때문에 특별히 목적을 부여 해주지 않아도 되는 경우가 많습니다. 따라서 ‘Add’에 비해 to나 for가 함께 사용되는 경우가 적습니다.

```

```

#### Implement A to B

> B를 위해 A를 구현합니다

구현 목적을 설명할 필요가 있을 때에는 ‘to’를 사용합니다.

```

```

### REVISE

Update와 비슷하나 문서의 개정이 있을 때 주로 사용합니다.

#### Revise A

> A 문서를 개정합니다

```

```

### CORRECT

주로 문법의 오류나 타입의 변경, 이름 변경 등에 사용합니다.

#### Correct A

> A를 고칩니다

```

```

### ENSURE

무엇이 확실하게 보장받는다는 것을 명시합니다. if 구문처럼 조건을 확실하게 주었을 때에도 사용 될 수 있습니다. ‘Make sure’도 같은 용도로 사용될 수 있습니다.

#### Ensure A

> A가 확실히 보장 되도록 수정했습니다

```

```

### PREVENT

특정한 처리를 못하게 막습니다

#### Prevent A

> A하지 못하게 막습니다

```

```

#### Prevent A from B

> A를 B하지 못하게 막습니다

```

```

### AVOID

‘Prevent’는 못하게 막지만, ‘Avoid’는 회피합니다. if 구문으로 특정한 동작을 제외시키는 경우에도 사용 할 수 있습니다.

#### Avoid A

> A를 회피합니다

```

```

#### Avoid A if B, Avoid A when B

> B인 상황에서 A를 회피합니다

```

```

### MOVE

코드의 이동이 있을 때 사용합니다.

#### Move A to B, Move A into B

> A를 B로 옮깁니다

```

```

### RENAME

이름 변경이 있을 때 사용합니다.

#### Rename A to B

> A를 B로 이름 변경합니다

```

```

### ALLOW

Make와 비슷하지만, 허용을 표현할 때 사용합니다.

#### Allow A to B

> A가 B를 할 수 있도록 허용합니다

```

```

### VERIFY

검증 코드를 넣을 때 주로 사용합니다.

#### Verify A

> A를 검증합니다

```

```

### SET

변수 값을 변경하는 등의 작은 수정에 주로 사용합니다.

#### Set A to B

> A를 B로 설정합니다

```

```

### PASS

파라메터를 넘기는 처리에 주로 사용합니다.

#### Pass A to B

> A를 B로 넘깁니다

```

```


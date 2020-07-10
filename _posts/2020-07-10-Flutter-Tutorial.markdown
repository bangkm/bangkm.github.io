---
layout: post
title:  "Flutter 시작하기 Step 01"
categories: Flutter Dart
---

Installing Flutter, Plugin using Visual Studio Code


-----------


### Install Fullter SDK & Setting Platform in MacOS

[맥OS에서 설치](https://flutter-ko.dev/docs/get-started/install/macos)

### Setting Editor

[에디터 설정](https://flutter-ko.dev/docs/get-started/editor?tab=vscode)

### Sample create App using Visual Studio Code(VSC)

1. Run VSC
2. View → Command Palette
3. Select Flutter: New Project

**main() 메서드는 화살표(=>) 표기법을 사용**한다.

**StatelessWidget**을 상속받아 앱 자체를 위젯으로 만든다. Flutter에서는 정렬, 여백, 레이아웃 등이 모두 위젯.

**Scaffold** Widget은 홈 화면 위젯 트리를 구성하는 **app bar, title, body 속성을 제공**한다

Widget의 주된 역할은 **하위 위젯을 어떻게 표현할 지를 설명하는 build() 메서드를 제공**하는 것

- **Using External Library**

pubspec.yaml → dependencies 목록 안에 추가

---

## Add Stateful Widget

StatelessWidget은 변경 불가능... 속성을 변경할 수 없으며 모든 값이 final

**StatefulWidget**은 Widget의 수명동안 변경될 수 있는 상태를 유지. **최소 두 개 이상의 클래스가 필요**하다. 

1) StatefulWidget Class가

2) State Class의 instance를 생성

**→ StatefulWidget 클래스 자체는 변경이 불가능하지만 State 클래스가 위젯의 수명동안 상태를 유지**

❗Dart 언어에서 식별자 앞에 밑줄( _ )을 붙이면 Private이 적용된다

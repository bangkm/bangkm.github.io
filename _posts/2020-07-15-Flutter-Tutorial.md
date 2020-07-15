---
layout: post
title:  "Flutter 시작하기 Step 02"
categories: Flutter Dart
---

Using Visual Studio Code, Flutter Tutorial 02

해당 글은 "첫 Flutter 앱 작성하기 - 2부"에 대한 내용이다. 1부는 공식 홈페이지에 한글로 작성되어있기에 1부는 공식 홈페이지를 참고하여 코드 작성 후 읽어보길 바란다.

 [첫 Flutter 앱 작성하기 - 1부 보러가기](https://flutter-ko.dev/docs/get-started/codelab)

### Purpose

- ***Navigate to a new screen*** 

  즐겨찾기(Favorite) 버튼을 클릭한 항목을 새로운 화면에서 보여주기

플루터에서는 ***Navigator***는 앱 경로를 포함하여 ***Stack***으로 관리한다. 

Build 메서드 Scaffold 필드에 ***list 아이콘을 추가***한다. 유저가 list 아이콘을 클릭했을 때 저장된 즐겨찾기 항목을 포함한 새로운 경로를 Navigator에 푸시한다.

```dart
class _RandomWordsState extends State<RandomWords> {
  ...
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Startup Name Generator'),
        actions: [
          // New
          IconButton(icon: Icon(Icons.list), onPressed: _pushSaved),
          // onPressed -> 클릭 시 수행할 함수
          // END New
        ],
      ),
      body: _buildSuggestions(),
    );
  }
  ...
}
```

빌드 시 AppBar에 리스트 아이콘이 보여지는 것을 확인하고, RandomWordsState에 ***_pushSaved() 함수***를 추가한다.

```dart
void _pushSaved() { }
```

_pushSaved 함수에서 Navigator.push를 호출하여 경로를 네비게이터의 스택으로 푸시한다. 

```dart
void _pushSaved() {
    Navigator.of(context).push(
      MaterialPageRoute<void>(
        // NEW lines from here...
        builder: (BuildContext context) {
          final tiles = _saved.map(
            (WordPair pair) {
              return ListTile(
                title: Text(
                  pair.asPascalCase,
                  style: _biggerFont,
                ),
              );
            },
          );
          final divided = ListTile.divideTiles(
            context: context,
            tiles: tiles,
          ).toList();

          return Scaffold(
            appBar: AppBar(
              title: Text('Saved Suggestions'),
            ),
            body: ListView(children: divided),
          );
        }, // ...to here.
      ),
    );
  }
}
```



### 마치며...

아직까지 익숙하지가 않아 문법이 헷갈린다......... 😅


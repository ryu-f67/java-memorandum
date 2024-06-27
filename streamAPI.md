# streamAPI
## streamAPIとは
streamAPIを使用することで、コレクションや配列に対して集計や変換処理を行うことができる。  
中間操作と終端操作がある。
## 使用方法

```java
List<String> list = List.of("banana","peach","apple","lime","raspberry","melon","pear","orange","apricot","plum");

List<String> filterList = 
    // ListをStreamに変換(Streamの生成)
    list.stream()
    // 中間操作。例は5文字以上のものをフィルターする。
    .filter(s -> s.length() >= 5)
    // 終端操作。StreamからListに変換する。
    .collect(Collectors.toList());

System.out.println(filterList);

// 実行結果
// list内の5文字以上の要素のみのリストになっている。
// [banana, peach, apple, raspberry, melon, orange, apricot]
```
## 中間操作
stream内の要素に対して操作を行う。
## 中間操作のメソッド
### filter
条件を満たした値だけを抽出するメソッド
```java
List<String> list = List.of("banana","apple","lime","raspberry","melon");

System.out.println(list.stream()
        // 6文字以上の要素を抽出
        .filter(fruit -> fruit.length() >= 6)
        .collect(Collectors.toList()));

// 実行結果
// [banana, raspberry]
```
### sorted
ソートをするメソッド
```java
List<String> list = List.of("banana","apple","lime","raspberry","melon");

System.out.println(list.stream()
        // ソートを行う
        .sorted()
        .collect(Collectors.toList()));

// 実行結果
// [apple, banana, lime, melon, raspberry]
```
### limit
個数を限定するメソッド
```java
List<String> list = List.of("banana","apple","lime","raspberry","melon");

System.out.println(list.stream()
        // 5文字以上の要素を2つまでに限定して抽出する
        .filter(fruit -> fruit.length() >= 5)
        .limit(2)
        .collect(Collectors.toList()));

// 実行結果
// [banana, apple]
```
### distinct
重複をなくすメソッド
```java
List<String> list = List.of("banana","apple","lime","raspberry","apple","banana");

System.out.println(list.stream()
        // 重複をなくす
        .distinct()
        .collect(Collectors.toList()));

// 実行結果
// [banana, apple, lime, raspberry]
```
## 終端操作
Streamの中の要素を実際に処理する。
## 終端操作のメソッド
### count
要素数をカウントするメソッド
```java
List<String> list = List.of("banana","apple","lime","raspberry","melon");

System.out.println(list.stream()
        // 6文字以上の要素をカウント
        .filter(fruit -> fruit.length() >= 6)
        .count());

// 実行結果
// 2
```
### 

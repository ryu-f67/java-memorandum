# 繰り返し処理
## 繰り返し処理
繰り返し処理には、for 文とforeach 文と拡張 for 文がある。
## for 文
実行させたい処理の繰り返し条件を指定し、指定した終了条件に達するまで処理を繰り返す。
```java
for (初期化式;, 条件式;, 変化式){
  繰り返しの中で実行される処理
}
```
以下に例を示す。
```java:コード
for (int i = 0; i < 3; i++){
  System.out.println("i=" + i);
}

// 実行結果
// i=0
// i=1
// i=2
```
## 初期化式、条件式、変化式の省略
初期化式、条件式、変化式は不要であればそれぞれ省略することができる.
### 初期化式の省略
for 文の中で使用される変数がすでに宣言してある場合は初期化式を省略することができる。
```java:例
int i = 0;

for (; i < 3; i++){
  System.out.println("i=" + i);
}
```
### 条件式の省略
条件式を省略した場合、条件式が常に true となるため、繰り返し処理が終わることができず無限ループとなる。  
この場合、break 文などを使って繰り返し処理を抜ける必要がある。
```java:例
int sum = 0;

for (int i = 0; ; i++){
  sum += i;
  if (sum > 9){
    break;
  }
}

System.out.println("sum=" + sum);
```
### 変化式の省略
変化式を省略した場合、繰り返し処理が一回終わるごとに何も変更が行われないので条件式の評価が変わらず無限ループになる可能性がある。  
この場合、繰り返し処理の中で条件式の評価が変わるような処理を記述する必要がある。
```java:例
int i = 0;

for (; i < 5; ){
  i += 3;
  System.out.println("i=" + i);
}
```
## foreach 文
作成中
## 拡張 for 文
拡張for文は配列やコレクション（大きさが決まっていない配列のようなもの）の全要素に対して、順番に処理を行う。  
for文のように一部の要素を取り出す処理はできない。
```java
for (型 変数 : コレクションまたは配列){
  繰り返しの中で実行される処理
}
```
以下に例を示す。
```java:コード
List<Integer> numberList = List.of(10,16,28,33,7,18,94,59,71);

for (int num : numberList){
  if (num >= 50){
    System.out.println(num);
  }
}

// 実行結果
// 94
// 59
// 71
```

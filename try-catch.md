# 例外処理
## 例外処理の書き方
```java
public static void main(String[] args){
  try{
    // 処理;
  }catch(例外クラス1 変数1){
    // 変数1.printStackTrace();
    // 例外クラス1発生時の処理;
  }catch(例外クラス2 変数2){
    // 変数2.printStackTrace();
    // 例外クラス2発生時の処理;
  }finally{
    // 必ず最後に実行する処理
  }
}
```
## 非チェック例外
### IOException
入出力の例外が発生
### ClassNotFoundException
指定したクラスが見つからない
### FileNotFondException
指定したファイルが見つからない
## チェック例外
### ArithmeticException
ゼロ除算など算術演算における不具合
### NullPointerException
nullオブジェクトにアクセス
### IndexOutOfBoundsException
配列の範囲を超えたインデックス指定
### ArrayStoreException
配列に無効な型の値を格納
### ClassCastException
不適当なキャスト
### NoSuchFieldException
フィールドが見つからない
### NoSuchMethodException
メソッドが見つからない
### RuntimeException
実行時に例外が発生
### IllegalAccessException
クラスに不正にアクセスした
### NumberFormatException
不適切な文字列を数値に変換

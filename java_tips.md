## Javaメモ

### 失敗
ResultSetクラスからgetStringなどするとき
そもそもselectしていないカラムについて使うとNullでエラー落ちしてしまう。
select文が点在しすぎた時どうしよう。


### ファイルを読むとき
readLineも使いたいし、文字コードも指定したい。

    BufferedReader br = new BufferedReader
    (new InputStreamReader(new FileInputStream(csvFile),"SJIS"));

### JUnit 
例外のテストの書き方
#### Exceptionそのもののチェック
@Test(expected = HogeException.class)

#### 例外の中の情報を確認したいとき
try 〜 catch で囲んで、
catch内でcauseをとって細かく試験が可能



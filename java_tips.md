## Javaメモ

### 失敗
ResultSetクラスからgetStringなどするとき
そもそもselectしていないカラムについて使うとNullでエラー落ちしてしまう。
select文が点在しすぎた時どうしよう。


### ファイルを読むとき
readLineも使いたいし、文字コードも指定したい。

    BufferedReader br = new BufferedReader
    (new InputStreamReader(new FileInputStream(csvFile),"SJIS"));




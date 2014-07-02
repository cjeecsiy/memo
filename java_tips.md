## Javaメモ
### ファイルを読むとき
readLineも使いたいし、文字コードも指定したい。

    BufferedReader br = new BufferedReader
    (new InputStreamReader(new FileInputStream(csvFile),"SJIS"));




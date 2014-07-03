# シェルあれこれ

## コマンド

### wcコマンド
ファイルの行数のみ（ファイル名は表示させない）を出力させる

    wc -l < ファイル名

### echoコマンド
エスケープ文字を認識させる。

    echo "aaa\tbbb"

### awk
n行目のmフィールド目を取り出す(例は2行目の3番目フィールド)

    echo -e "aaa bbb ccc\nddd eee fff" | awk 'NR==2{print $3}'

## 設定(シェル変数など)
### LANG

OSの種類と、言語(日本語/英語)、文字コードによってことなる。
Cは翻訳しないだけでファイルの言語などが変わるわけではない。

|OS|言語の種類|設定値|
|-----|-----|-----|
|Linux|日本語(EUC)|ja_JP.eucJP，ja_JP.EUC|
||日本語(UTF-8)|ja_JP.UTF-8|
||英語|C|
OSはAIX,HP-UX,Solarisなど


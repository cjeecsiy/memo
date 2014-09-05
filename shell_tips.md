# シェルあれこれ

## コマンド

### dateコマンド
日付表示。
MacとLinuxでオプションが異なる

Mac

    $ date -v-13m +'%Y%m'

### echoコマンド
エスケープ文字を認識させる。

    echo "aaa\tbbb"

### seqコマンド

    # 13から1ずつ2まで減らす
    seq 13 -1 2


### nkfコマンド

    nkf --overwrite 同一ファイルに上書き
    
    -g --guess 文字コード判別
    -w UTF-8変換
    -s SJIS変換
    -e EUC-JP変換
    -Lu LF変換
    -Lw CRLF変換
    -Lm CR変換

### wcコマンド
ファイルの行数のみ（ファイル名は表示させない）を出力させる

    wc -l < ファイル名

### awk
n行目のmフィールド目を取り出す(例は2行目の3番目フィールド)

    echo -e "aaa bbb ccc\nddd eee fff" | awk 'NR==2{print $3}'

上記例は、こんな風にも取得可能。

    awk '{getline;print $3}'


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


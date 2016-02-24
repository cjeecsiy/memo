#Excelショートカット集
覚え書きなので  
最近覚えたものほど上に書いて行きます  

 * `Ctrl`+`6` 画像非表示**（誤爆注意）**
 * `Ctrl`+`:` 現在時刻(hh:ss)
 * `Ctrl`+`;` 今日の日付(yyyy/mm/dd)
 * `Ctrl`+`5` 取り消し線
 * `Ctrl`+`Shift`+`L` フィルタ
 * `Ctrl`+`B` 太字

2007以降？
 * `Alt`+`1~0` 任意のショートカットとして登録可能
     セル結合などにオススメ。


## 比較マクロ

シート間の比較を行い、差があれば色付けするマクロ
結構便利でした。
http://gihyo.jp/book/pickup/2009/0021
テーブル構造もった定型ページとかもコピペして比較するだけなので楽。

```
Sub hikaku()
    Dim RETSU_S, RETSU_E, GYOU_S, GYOU_E As Integer
    RETSU_S = 1 '列をBから
    RETSU_E = 200 '列をFまで
    GYOU_S = 1  '行を3から
    GYOU_E = 200 '行を12まで

    Dim s1, s2 As Worksheet 'Worksheetsオブジェクト用
    Set s1 = Worksheets("OldSheet") '比較元シート名
    Set s2 = Worksheets("NewSheet") '比較先シート名

    Dim r1 As Range 'Rangeオブジェクト用

    Dim retsu, gyou As Integer 'この変数で列と行を指定する

    For retsu = RETSU_S To RETSU_E
        For gyou = GYOU_S To GYOU_E
            s1.Cells(gyou, retsu).Interior.ColorIndex = 2
            s1.Cells(gyou, retsu).ClearComments
            If s1.Cells(gyou, retsu).Value <> s2.Cells(gyou, retsu).Value Then
                Set r1 = s1.Cells(gyou, retsu)
                If TypeName(r1.comment) = "Nothing" Then r1.AddComment
                r1.comment.Text Text:=CStr(s2.Cells(gyou, retsu).Value)
                r1.Interior.ColorIndex = 6
            End If
        Next
    Next
```



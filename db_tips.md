
# DBメモ
  
## SQL
#### 更新対象のテーブル以外のテーブルの条件一致を元にテーブルを更新する
##### [Oracle]

    UPDATE tableA 
    SET columnA = 'Y' 
    WHERE columnA = 'N'
      AND EXISTS (
        SELECT columnA 
        FROM tableA A, tableB B 
        WHERE A.columnAPK = B.columnB )

#### CREATE TABLE と同時に INSERT SELECT する方法
##### [Oracle]

    CREATE TABLE tableA AS select_strings

## DB総合
### ロールバック領域
１つのトランザクションに対してロールバック時の復旧データを保持する領域。
ロールバック領域を使い果たしてしまった場合、
現在のトランザクションが終わっていなくてもロールバック領域を上書きをしてしまうため、
復旧できなくなるらしい。

## Oracle  

- [OracleSQLトレースログの出し方](http://d.hatena.ne.jp/replication/20130110/1357824989)  

#### おおよそのpath：oracle/diag/rdbms/xe/xe/trace  
#### 設定

    ALTER SYSTEM SET SQL_TRACE = TRUE;  

トレース用ディレクトリ配下にxxx.trcというファイルができるようになるので  
中を確認すると、実行されたSQLが表示される  
  
バインド変数もだせるようになるらしい  
設定するレベルによってトレースの粒度が異なる。  

    ALTER SYSTEM SET EVENTS '10046 trace name context forever, level 4';  

1. Level 1 -> SQLトレースだけ  
2. Level 4 -> SQLトレースとバインド変数  
3. Level 8 -> SQLトレースと待機イベント  
4. Level 12 -> SQLトレースとバインド変数と待機イベント  
  
戻し方  

    ALTER SYSTEM SET SQL_TRACE = FALSE;  
    ALTER SYSTEM SET EVENTS '10046 trace name context off';  

## mysql

### homebrewでインストールしたMYSQLが上手く動かないときのtips

まずhomebrewからの情報の確認方法

    brew info mysql

設定手順や起動方法など表示されるので確認する。  

参照[HomebrewでMySQLをインストールする時に知っておきたいこと](http://tukaikta.blog135.fc2.com/blog-entry-197.html)





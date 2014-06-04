
# DBメモ
  
## Oracle
  
-[OracleSQLトレースログの出し方](http://d.hatena.ne.jp/replication/20130110/1357824989)
おおよそのpath：oracle/diag/rdbms/xe/xe/trace  
設定

    ALTER SYSTEM SET SQL_TRACE = TRUE;  

トレース用ディレクトリ配下にxxx.trcというファイルができるようになるので  
中を確認すると、実行されたSQLが表示される  
  
バインド変数もだせるようになるらしい  
設定するレベルによってトレースの粒度が異なる。  

    ALTER SYSTEM SET EVENTS '10046 trace name context forever, level 4';  

1.Level 1 -> SQLトレースだけ  
2.Level 4 -> SQLトレースとバインド変数  
3.Level 8 -> SQLトレースと待機イベント  
4.Level 12 -> SQLトレースとバインド変数と待機イベント  
  
戻し方  

    ALTER SYSTEM SET SQL_TRACE = FALSE;  
    ALTER SYSTEM SET EVENTS '10046 trace name context off';  





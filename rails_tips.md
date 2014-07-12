# railsぷちかじりmemo

## 引数の取り方
 - [RubyLife パラメータの取得](http://www.rubylife.jp/rails/controller/index6.html)
 - [-](http://railsdoc.com/references/params)

# rvm

## バージョン確認 

    rvm -v 

## バージョンアップ

    rvm get stable

### rvm 
こんなエラーが出た。    
    
        RVM is not a function, selecting rubies with 'rvm use ...' will not work.
	rvmのbundleなどのサブコマンドにパスを通す為のものを書き忘れたらしい。
	.bashrcに下記を記述すると出なくなった。

	    source "$HOME/.rvm/scripts/rvm"


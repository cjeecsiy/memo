# railsぷちかじりmemo

## 引数の取り方
 - [RubyLife パラメータの取得](http://www.rubylife.jp/rails/controller/index6.html)
 - [-](http://railsdoc.com/references/params)

# rvm

## バージョン確認 

    rvm -v 

## バージョンアップ

    rvm get stable

### エラー
    
    RVM is not a function, selecting rubies with 'rvm use ...' will not work.

rvmのbundleなどのサブコマンドにパスを通す為のものを書き忘れたらしい。
.bashrcに下記を記述すると出なくなった。

    source "$HOME/.rvm/scripts/rvm"

### 

    /Users/cjeecsiy/.rvm/gems/ruby-2.0.0-p481@railstutorial_rails_4_0/gems/activerecord-4.0.4/lib/active_record/migration.rb:383:in `check_pending!': Migrations are pending; run 'bin/rake db:migrate RAILS_ENV=test' to resolve this issue. (ActiveRecord::PendingMigrationError)

### DBリセットと再設定

    rake db:reset
    rake db:migrate RAILS_ENV=development
    rake test:prepare


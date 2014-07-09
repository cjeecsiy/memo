# gitメモ

リモートリポジトリを設定

    $ git remote add ${remote-name} ${url}


リモートリポジトリの確認

    $ git remote -v


リモートリポジトリの削除

    $ git remote rm ${remote-name}


リモートへの更新(git pushに省略可能)

    $ git push -u ${remote-name} master


コミット対象として登録

    $ git add ${commit-file-path}


コミット

    $ git commit -m "コメントメッセージ"

コミット内容の修正

    $ git commit --amend


以前のコミット内容に戻す(revert)

    $ git checkout -f


ステータスの確認(svn -u st)

    $ git status


リポジトリのチェックアウト

    $ git clone https://github.com/*****/****.git

ブランチの確認(remoteも確認したい場合は-a)

    $ git branch

ブランチの作成

    $ git checkout -b ${newブランチ名}

rspecの実行

    $ git exec rspec spec/requests/static_pages_spec.rb 


## 用語の意味

### fork
他所のリポジトリを複製し、共同開発する。  
forkしたデータは、オリジナルとして自由に更新が出来る。  
fork内のデータはfork元の開発者に更新依頼をすることが可能。  
簡単に共同開発するための仕組み。  

### rvm
rvmのbundleなどのコマンドにパスを通す為のもの
.bashrcなどに書くのを忘れると泣きをみるので注意。

    source "$HOME/.rvm/scripts/rvm"




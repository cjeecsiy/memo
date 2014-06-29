#gitメモ

- リモートリポジトリを設定

    $ git remote add ${remote-name} ${url}

- リモートリポジトリの確認

    $ git remote -v 

- リモートリポジトリの削除

    $ git remote rm ${remote-name}

- リモートへの更新(git pushに省略可能)

    $ git push -u ${remote-name} master

- コミット

    $ git commit -m "コメントメッセージ" 

- コミット対象として登録

    $ git add ${commit-file-path} 

- 以前のコミット内容に戻す(revert)

    $ git checkout -f

- ステータスの確認(svn -u st)
    
    $ git status

- リポジトリのチェックアウト
    
    $ git clone https://github.com/*****/****.git


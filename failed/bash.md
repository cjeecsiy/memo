# 激しく間違えたことを書くメモ
こんなの絶対繰り返したくないッ！
## for文でファイルを全部リセットしてしまった。
<pre><code>for file in `find . -type f | grep -v '.svn'`; do echo $file; cat $file | sed -e 's/foo/var/g' > $file ; done  </code></pre>
$fileを入力して$fileに書き込んでいるため、ファイルサイズがゼロになってしまった。  
あんまりだ。。  
正しくは下記のように一旦別ファイルに書き込む。
<pre><code>for file in `find . -type f | grep -v '.svn'`; do echo $file; cat $file | sed -e 's/foo/var/g' > $file.tmp ; mv $file.tmp $file ;done </code></pre>

## cronデータ消しちゃった
禁断の呪文

    crontab -r
    
-eのつもりが誤った。事前に必ず

    crontab -l
    
しておこう。
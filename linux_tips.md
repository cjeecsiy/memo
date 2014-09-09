# Linux系あれこれ

## rsyslog
 
  rsyslogを使用し、普段はリモートサーバにログを送り、
  リモートがダウンしたときにはローカル内に保存させるようにしたいが、
  ログがキューイングされない。
  → /etc/rsyslog.confの設定の書き方が誤っているかも、コメント行をなくして一度に連続で書くと上手くいくらしい？

    $WorkDirectory /var/spool/rsyslog # where to place spool files
    $ActionQueueFileName fwdRule1 # unique name prefix for spool files
    $ActionQueueMaxDiskSpace 1g # 1gb space limit (use as much as possible)
    $ActionQueueSaveOnShutdown on # save messages to disk on shutdown
    $ActionQueueType LinkedList # run asynchronously
    $ActionResumeRetryCount -1 # infinite retries if host is down
    *.* @@remote-host:514



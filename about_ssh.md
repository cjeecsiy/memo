SSHあれこれ
============

作った鍵ペアが正しいかの確認
通常ないと思うけれど、何かの拍子に正しい鍵がわからなくなってしまったとき
■公開鍵
ssh-keygen -l -f .ssh/authorized_keys
■秘密鍵
ssh-keygen -l -f .ssh/id_rsa

#どちらも同じコマンドでできてしまうなんて…


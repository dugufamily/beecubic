# beecubic
private work
添加私钥
$ ssh-add ~/.ssh/id_rsa
$ ssh-add ~/.ssh/id_rsa_github
如果执行ssh-add时提示"Could not open a connection to your authentication agent"，可以现执行命令：

$ ssh-agent bash
然后再运行ssh-add命令。

# 可以通过 ssh-add -l 来确私钥列表
$ ssh-add -l

# 可以通过 ssh-add -D 来清空私钥列表
$ ssh-add -D
修改配置文件
在 ~/.ssh 目录下新建一个config文件

touch config
添加内容：

# gitlab
Host gitlab.com
    HostName gitlab.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa

# github
Host github.com
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_github
测试
$ ssh -T git@github.com
输出
Hi user! You've successfully authenticated, but GitHub does not provide shell access. 就表示成功的连上github了

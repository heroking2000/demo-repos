*github-setup* github安装 |github|

github.com是git公共资源平台，任何人均可以申请一个免费的git资源空间。

注册成功后，需要将自己的SSH Key添加到github.com中，首先在~/.ssh/目录下生成密钥文件
$ ssh-keygen -t rsa -C "heroking2000@163.com" -f id_rsa_github

并将公钥拷贝到Add an SSH Key的Key字段中
$ xclip -sel clip < id_rsa_github.pub

编辑~/.ssh/config文件
Host  github
    Hostname github.com
    User git 
    IdentityFile  ~/.ss h/id_rsa_github

修改config文件权限
$ chmod 600 ~/.ssh/config
否则在交换密钥时提示Bad owner or permissions on ~/.ssh/config

与github交换密钥
$ ssh -T git@github.com

然后在github.com上创建一个资源项目demo-repos，本地获取该资源
$ git clone github:heroking2000/demo-repos.git

在当前资源库上配置user.name和user.email
$ git config user.name "heroking2000"
$ git config user.email "heroking2000@163.com"

本地提交
$ git commit -am "fix message"

远程提交
$ git push

GoAgent代理设置
$ git --config http.proxy http://127.0.0.1:8087/
$ git --config http.sslVerify false




vim:tw=78:ts=8:ft=help:norl:

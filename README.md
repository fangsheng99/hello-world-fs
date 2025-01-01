# hello-world-fs
## 开始使用github
### 1.部署本地Git与Github连接（SSH）

a.设置自己的用户名和密码,userName和emailAddress替换成自己想要的即可，建议username用英文名：
git config --global user.name "userName"  //你的用户名
git config --global user.email "emailAddress" //你的邮箱地址

b.创建一个ssh key（密钥），代码：
ssh-keygen -t rsa -C"上面的emailAddress"
注意C必须大写

c.连续回车，如果显示：
Saving key "/Users/fangsheng/.ssh/id_rsa" failed: Not a directory
说明没有这个目录。原因：已经存在的.ssh并不是一个文件夹，可以删除已有的 .ssh，再重新ssh-keygen就会有.ssh文件夹

d.删除 .ssh命令：rm -rf .ssh

e.重新用以下命令创建：
ssh-keygen -t rsa -C"上面的emailAddress"

f.用以下代码查看密钥：
cat /Users/fangsheng/.ssh/id_rsa.pub

g.添加到github，然后用以下命令检查是否添加成功：
ssh -T git@github.com

h.如果有以下报错：
ssh: connect to host github.com port 22: Operation timed out
输入以下命令：
host github.com
User 上面的emailAddress
Hostname ssh.github.com
PreferredAuthentications publicly
IdentityFile ~/.ssh/id_rsa
Port 443

i.再次执行以下命令：
ssh -T git@github.com

j.出现以下内容即为成功：
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi fangsheng99! You've successfully authenticated, but GitHub does not provide shell access.

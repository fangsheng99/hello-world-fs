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

# Learn_Git
Git
### 版本控制分类
- 本地版本控制
记录文件每次的更新，可以对每个版本做一个快照，或是记录补丁文件，适合个人用，如RCS。  
- 集中版本控制 (SVN)
所有的版本数据都保存在服务器上，协同开发者从服务器上同步更新或上传自己的修改。
- 分布式版本控制 (GIT)
所有版本信息仓库全部同步到本地的每个用户，这样就可以在本地查看所有版本历史，可以离线在本地提交，  
只需在连网时push到相应的服务器或其他用户那里。由于每个用户那里保存的都是所有的版本数据，只要有  
一个用户的设备没有问题就可以恢复所有的数据，但这增加了本地存储空间的占用。

### git和svn的区别？
- SVN是集中式版本控制系统，版本库是集中放在中央服务器的，而工作的时候，用的都是自己的电脑所以  
首先要从中央服务器得到最新的版本，然后工作，完成工作后，需要把自己做完的活推送到中央服务器。集  
中式版本控制系统是必须联网才能工作，对网络带宽要求较高。
- Git是分布式版本控制系统，没有中央服务器，每个人的电脑就是一个完整的版本库，工作的时候不需要  
联网了，因为版本都在自己电脑上。协同的方法是这样的∶比如说自己在电脑上改了文件A，其他人也在电  
脑上改了文件A，这时，你们两之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。  
Git是目前世界上最先进的分布式版本控制系统。

## 常见基础的Linux命令
1. cd： 改变目录
2. cd.. 回退到上一个目录，直接cd进入默认目录
3. pwd：显示当前所在的目录路径
4. ls(ll)：列出当前目录中的所有文件，只不过ll列出的内容更加详细
5. touch：新建一个文件 如touch index.js 就会在当前目录下新建一个index.js文件
6. rm：删除一个文件， rm index.js 就会把index.js文件删除
7. mkdir：新建一个目录(文件夹)
8. rm -r：删除一个文件夹，rm -r src 删除src目录
9. mv：移动文件，mv index.html src ，index.html是我们要移动的文件，src是目标文件夹，当然，这样写必须文件和文件夹在同一个目录下
10. reset：重新初始化终端/清屏
11. clear：清屏
12. history：查看历史命令
13. help：帮助
14. exit：退出
15. #：表示注释




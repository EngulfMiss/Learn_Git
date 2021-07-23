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
2. cd .. 回退到上一个目录，直接cd进入默认目录
3. pwd：显示当前所在的目录路径
4. ls(ll)：列出当前目录中的所有文件，只不过ll列出的内容更加详细
5. touch：新建一个文件 如touch index.js 就会在当前目录下新建一个index.js文件
6. rm：删除一个文件， rm index.js 就会把index.js文件删除
7. mkdir：新建一个目录(文件夹)，创建多级目录加 -p
8. rm -r：删除一个文件夹，rm -r src 删除src目录
9. mv：移动文件，mv index.html src ，index.html是我们要移动的文件，src是目标文件夹，当然，这样写必须文件和文件夹在同一个目录下
10. reset：重新初始化终端/清屏
11. clear：清屏
12. history：查看历史命令
13. help：帮助
14. exit：退出
15. #：表示注释

## git的配置
- 查看git的配置: git config -l
- 查看系统的配置：git config --system --list
- 查看本地(用户)的配置：git config --global --list

- 设置git用户名(必须)：git config --global user.name "MildLamb"
- 设置git邮箱地址(必须)：git config --global user.email "121*****45@qq.com"

## Git基本理论(核心)
- 工作区域
Git本地有三个工作区域 工作目录(Working Directory)，暂存区(Stage/index)，资源库(Repository或Git Directory)。  
如果再加上远程的git仓库(Remote Directory)就可以分为四个工作区域。  
![I88F{A}FYR( VM6PDBNS 84](https://user-images.githubusercontent.com/61497283/126729560-80058486-b446-40cf-a707-24df84bb9a56.png)
  - Workspace :工作区，就是你平时存放项目代码的地方
  - Index / Stage:暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息
  - Repository :仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本
  - Remote :远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换  

## Git项目搭建
![U UVBX(V$73 HL}6N AAU2J](https://user-images.githubusercontent.com/61497283/126730274-53b8c0a0-c00b-480c-a3a7-3c9ff932f8a3.png)

**创建本地仓库的方法有两种：一种是创建全新的仓库，另一种是克隆远程仓库**  
- git init:本地创建
- git clone [url]:远程克隆

## Git文件操作
文件有4种状态：  
- Untracked:未跟踪，此文件在文件夹中，但并没有加入到git库，不参与版本控制。通过**git add**状态转变为**Staged**
- Unmodify:文件已经入库，未修改，即版本库中的文件快照内容与文件夹完全一致，这种类型的文件有两种去处，如果它被修改  
则变为**Modified**.如果使用**git rm**移出版本库，则变为**Untracked**文件
- Modified:文件已修改，仅仅是修改，并没有进行其他操作，这个文件也有两种去处，通过**git add**可进入暂存**staged**状态  
，使用**git checkout**则丢弃修改过，返回到**unmodify**状态，这个**git checkout**即从库中取出文件，覆盖当前修改！  
- Staged:暂存状态，执行**git commit**则将修改同步到库中，这时库中的文件和本地文件变为一致，文件为**Unmodify**状态。  
执行**git reset HEAD filename**取消暂存，文件状态为**Modified**

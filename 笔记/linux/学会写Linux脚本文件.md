[TOC]

# 学会写Linux脚本文件

脚本文件是用来执行一系列命令的，就是为了偷懒，比如我想把我们的笔记上次到github。但是我不想每次都输入那些命令，那就写个脚本文件了，只有配好环境变量或者放到合适的位置，就可以直接输入脚本文件的名字就可以执行了。

首先你要知道脚本文件是一个可执行文件，所以你要给他可执行的权限(在linux中只要一个文件有执行权限，他就可以被执行)。

# 开始

我们的一般可执行文件都放在：/usr/bin/       或者是/usr/local/bin/      这两个目录下，但是第一个是我们安装的软件会放一些可执行文件在这里，ls命令其实也是放在这里，python也是在这里，所以你也可以放这里。第二个是本地的，我们自定义的脚本可以放在里面，方便管理。这两个目录都是在我们的环境变量里面的。你可以用该命令：echo   &PATH   自己看看是不是。

文件的命名：你可以以  .sh   结尾，但是前面说了，只要有执行权限就可以执行！！创建一个文件，名为autoUpdate.sh，然后编辑他 ，他的内容如下：

~~~
#!/bin/sh
# 顶部这个代表声明他是一个可执行文件
# touch /home/ba/log/log.text   假设你想要有日志输入，看看执行到了哪句，你可以创建一个日志文件(存在的话他不会创建)
cd /home/ba/AndroidStudioProjects/BANote
git add .
git commit -m "笔记"
git pull
git push
# 下面这句就是输出文字到指定位置
echo “上传成功” >>  /home/ba/log/log.text   
# 在linux中#号后面的句子是注释，所有需要执行的命令写在exit 0的前面，exit 0代表执行完退出终端
exit 0;  
~~~

---

保存后，当然要改权限：chmod    -x    autoUpdata.sh



ok啦！ 你可以试试直接输入autoUpda然后按下tab键，是不是就出来啦！






























































































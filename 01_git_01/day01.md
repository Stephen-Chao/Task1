##1.版本控制管理工具
    集中式版本控制管理
        SVN,CVS
    分布式版本控制管理
        git
        git是为了管理Linux的内核代码而出现的
##2.Shell命令
    linux系统中
####    1.    pwd,cd,ls
        pwd:
            print working directory
            打印当前工作路径(显示当前路径位置)    
        cd: 
            change directory
            改变工作路径(切换文件夹)
            cd .. 切换到上一级目录
            cd a 切换到当前目录下的a目录中
            cd ./a 同上
            cd /c/users 以绝对路径的方式切换到c盘下的users文件夹下
            cd~ 切换到当前登录用户的主目录中
                ~表示当前登录用户的主目录
        ls:
            list 显示当前目录下的所有非隐藏文件或目录
            ls
            ls-a 显示所有的,包括隐藏的
                linux中文件的隐藏是通过在文件名前加.实现
            ls-lt 以列表的形式按时间顺序显示文件或目录    
                l表示list以列表显示,t表示time按时间顺序
####    2. 创建文件夹
        mkdir make directory
        mkdir 目录名称
        mkdir a 在当前路径下创建a目录
        mkdir ./a 同上
        如果目录已存在,则报错
        
        mkdir ./a/b 在当前路径下的a目录中创建b目录
            如果a目录不存在,则报错
        mkdir -p ./a/b 如果a目录不存在,则先创建a目录
        
        mkdir a ../b 同时创建多个目录
####    3.创建文件
        touch 文件名     
        touch 的文件名如果不存在,则创建一个文件
        若果touch的文件名(目录名)存在,则修改该文件(目录)的最后访问时间     
####    4.向文件中写入数据
        1) echo
            echo 数据 > 文件名(覆盖模式)
            如果文件不存在,则自动创建
            echo 数据 >> 文件名(追加模式)
        2)vi 文本编辑工具 
            vi 文件名 (如果不存在,则自动创建)
            vi打开文件后,自动进入到命令模式,此时不可以输入数据,但是可以切换到其他两种模式:
                输入模式:按a/i进入,左下角显示--插入--,此时可以输入数据,输入结束后,按esc退出输入模式,重新进入命令模式
              
                底行模式:按:进入,左下角显示:,此时输入回撤重新进入命令模式,或者按wq保存退出vi界面
                    wq:保存并退出
                    w:保存不退出
                    q:退出
                    q!:不保存,强制退出   
####    5.查看文件内容
        cat catch
        cat 文件名
####    6.删除文件
        rm remove
        rm 文件名
####    7.删除目录
        rmdir remove directory
        rmdir 目录名
        该命令只能删除空目录
        若要删除非空目录,使用 rm -rf 目录名    

##3.git的使用
    所有的git命令都是以git开头的
    如:查看git版本号 git --version
    1)配置用户个人信息
        git config --global user.name "用户名"
        git config --global user.email "邮箱地址"
    2)初始化本地仓库(创建本地的版本库)
        git init
        先切换到目标目录,然欧输入git init命令
        将当前目录初始化为本地仓库
        自动生成一个.git的隐藏文件夹,该文件夹就是版本库
    3)查看本地仓库的状态
        git status
    4)提交
        -1 git add 文件名
        
        -2 git commit -m "提交信息"   
            将暂存的文件提交到版本库中

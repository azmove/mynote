Mac OS X Terminal 打开Tab键自动补全功能
打开Terminal应用程序 
输入 nano .inputrc

再输入以下语句：

set completion-ignore-case on
set show-all-if-ambiguous on
TAB:menu-complete

输入完毕后 
按下 Control ＋ o 
然后关闭、重启

---------------------------------

mac安装神器brew
安装方法:命令行输入 
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"   
回车（这里有提示目录不存在，要创建需要按return键，如果用的windows键盘，就是回车键）

它的用法

brew update  更新brew；

brew install {应用名，如git} 安装软件

brew cask install {应用名，如git} 也是下载安装，与上面的区别，请查看https://www.zhihu.com/question/22624898

更多用法请 brew help
----------------------------------
mac 升级GIT和配置GIT
Mac 系统自带GIT，但是自带的GIT 版本很老，也没有自动提示和gitk等功能，如果一个一个去安装非常的费劲。

我们采用brew 安装git 非常的方便，但是，我们发现安装后没有任何作用，因为默认使用的GIT还是老版本的。

为了解决大家和我一样的问题，我现在写下我的解决办法，希望能够帮助到大家。

1.使用brew安装git ,brew install git

2.备份旧的GIT 目录，cd /usr/local/bin

                         ls git*

                         mkdir backup-git

                         mv git* ./backup-git/
3.到新的git目录。cd /usr/local/Cellar/git/2.1.3

看到git已经安装成功
cd ~

vim .bash_profile 添加 export GIT=/usr/local/Cellar/git/2.1.3

export PATH=$GIT/bin:$PATH

6.刷新环境变量 source .bash_profile

到此，就都安装配置成功了，可以体验最新版的GIT功能了。
# vim-config
vim配置
https://github.com/LiuFeiChen/vim-go-ide.git
https://github.com/broqiang/vim-go-ide.git  #这是fork的vim针对go环境配置的项目，在根据步骤做的过程中出现一些问题，现在针对出现的问题做对应的处理
https://github.com/LiuFeiChen/vim-go-ide.git

1.教程使用的系统时ubuntu18但是我使用的是centos7，但是vimrc不使用教程里的那个针对centos的，就使用里面那个vimrc文件
2. GoInstallBinaries进行go的一些依赖包安装的时候因为golang.org被墙了所以需要单独从github拉取并安装，下面是安装步骤
     
	git clone https://github.com/golang/tools.git src/golang.org/x/tools 
	git clone https://github.com/golang/sync.git src/golang.org/x/sync 
	git clone https://github.com/golang/net.git src/golang.org/x/net 
	git clone https://github.com/golang/xerrors.git src/golang.org/x/xerrors 
	go install golang.org/x/tools/...
	git clone https://github.com/golang/lint.git src/golang.org/x/lint 
	go install golang.org/x/lint
	
	上面安装完成后就可以正常GoInstallBinaries了
3.vim升级 #因为插件fatih/vim-go要求的版本是8以上，所以需要下载源码进行编译安装https://www.vim.org/download.php下载最新版本
   如果不进行配置直接编译的话后面打开vim的会报YouCompleteMe unavailable: requires Vim compiled with Python 2.x support等相关错误，
  ./configure --prefix=/usr --enable-multibyte --enable-pythoninterp=yes  --enable-python3interp=yes --enable-multibyte    #这样配置后就可以了
  make ; make install


4.自动提示功能支持
```
在.vimrc的插件配置中加入下面的2行配置，然后打开vim执行:PlugInstall, 安装成功后使用<C-x><C-o>即可出现代码提示，github：https://github.com/nsf/gocode
" go 自动提示
Plug 'nsf/gocode', {'rtp': 'vim/'}

python代码提示https://github.com/davidhalter/jedi-vim
```

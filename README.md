# vim-config

## 说明
因plugged目录压缩包大于100MB，所以被存放在百度网盘了
`链接: https://pan.baidu.com/s/1LoKzr1pEySBWAlwxmqsydw 提取码: v5pg 复制这段内容后打开百度网盘手机App，操作更方便哦`
下载plugged.tar.gz至.vim目录下解压即可

## 依赖
主要还是ycm的依赖，
`https://github.com/ycm-core/YouCompleteMe#requirements`

## 安装
除了ycm需要重新编译，plugged下面的插件都可以直接使用
`cd /root/.vim/plugged`
![1667652687733](https://user-images.githubusercontent.com/17865744/200120762-fc5deece-2731-4753-92c8-2ddcb8f7c7de.png)
```
cd YouCompleteMe
python3 install.py  --clang-completer --go-completer --ts-completer 
根据需要选择后面的参数，表示支持那些语言，如果要所以的话--all即可，-h查看支持那些语言
可能因为网络的问题无法下载，需要自己修改脚本，自己下载

```

## ycm自动补全

自定义配置参考： https://github.com/LiuFeiChen/dotfiles

1.全局配置： 通过配置let g:ycm_global_ycm_extra_conf='~/.vim/.ycm_extra_conf.py'来指定自己的补全配置，这是全局的配置
`https://github.com/LiuFeiChen/dotfiles/blob/master/YouCompleteMe/ycm_extra_conf.py`

2.C语言项目配置,将下面的链接的文件拷贝至工程的顶层目录，并重命名为： .ycm_extra_conf.py
`https://github.com/LiuFeiChen/dotfiles/blob/master/YouCompleteMe/ycm_extra_conf.py`

3.C++语言项目配置,将下面的链接的文件拷贝至工程的顶层目录，并重命名为： .ycm_extra_conf.py
`https://github.com/LiuFeiChen/dotfiles/blob/master/YouCompleteMe/ycm_cpp_conf.py`

4.python和go无需配置已经支持补全了



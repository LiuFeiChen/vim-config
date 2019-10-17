# python在vim里面可以自由的进行函数和变量的跳转

1. 下载ptags.py

   wget http://svn.python.org/projects/python/trunk/Tools/scripts/ptags.py
   
   mv ptags.py  ptags  && chmod +x prtags && mv ptags /usr/bin
   
2. 生成第三方库的tags文件

    我的第三方库安装目录为/usr/local/lib64
    
    find  /usr/local/lib/python3.6/site-packages -name \*.py -print | xargs ptags
    
    mv tags third_party_library_tags
    
3. 生成python系统库的tags文件

    find /lib64/python3.6 -name \*.py -print | xargs ptags
    
    mv tags python_system_tags
    
4. 生成当前工程的tags

   find  . -name \*.py -print | xargs ptags
   
5.合并第三方和系统的tags到当前工程tags中

   cat third_party_library_tags >> tags
   
   cat python_system_tags >> tags
   
通过上面的操作后，就可以在vim中进行第三方，系统，当前工程之前跳转

如果官网下载ptags失败，可以直接使用配置工程里面的ptags.py

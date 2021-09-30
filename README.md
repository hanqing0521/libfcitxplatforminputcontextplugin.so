### 2021-09-30 更新
Mathematica 12 for linux用的Qt版本为Qt5.11.0 
```bash
strings libQt5Core.so.5 |grep -i "qt 5"
Qt 5.11.0 (x86_64-little_endian-lp64 shared (dynamic) release build; by GCC 6.3.1 20170216 (Red Hat 6.3.1-3))
This is the QtCore library version Qt 5.11.0 (x86_64-little_endian-lp64 shared (dynamic) release build; by GCC 6.3.1 20170216 (Red Hat 6.3.1-3))
If that is not possible, in Qt 5 you must at least reimplement
```
恰好在github找到qt5.11编译的libfcitxplatforminputcontextplugin.so文件，免去自己辛苦编译了，谢谢作者，如果有其他人碰到mathematica无法使用fcitx输入中文可借鉴，将符合要求的libfcitxplatforminputcontextplugin.so文件放置于`/usr/local/Wolfram/Mathematica/12.0/SystemFiles/Libraries/Linux-x86-64/Qt/plugins/platforminputcontexts`
### 2018-12-08 更新

最新的 RStudio 版本为 1.2.1114，Qt 版本为 Qt-5.11.1。RStudio 自带的 `libQt5*` 文件保存在 `/usr/lib/rstudio/lib` 下，`2018-08-16 更新`的方法移除这些文件的办法又失效了。
所以现在又一次需要自己编译了。NOT Peace...

### 2018-08-16 更新
现在这个问题似乎有了新的办法，详见我的博客 [解决 Debian 中 RStudio 和 Mendeley 下 Fcitx 输入法不能使用的问题 #12](https://github.com/JackieMium/my_blog/issues/12) 开头部分的更新。

希望这是一个真正的稳定的办法，那样的话我这个 repo 大概也就没有存在的必要了吧，这也是我希望看到的。Peace...


# 解决 Fcitx 输入法在一些 qt5 程序下无法使用的问题。
我提供的 `libfcitxplatforminputcontextplugin.so` 都是在 Debian sid 中编译通过。详细支持的应用和 QT 版本见文件夹下的 `README` 内容。
目前支持应用：

- Mendeley Desktop
- RStudio
- Mathematica 12

# MacOS在命令行中打开Sublime Text 3

# 配置

在终端中输入命令来创建软链接：

```bash
ln -sv "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

如果Sublime Text是版本v2，则使用如下命令：

```bash
ln -sv "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

然后

```bash
source ~/.zshrc
```

# 使用

在命令行执行：

```bash
subl text.cpp
```

就可以直接打开文件啦。

# Reference

1. [Launch Sublime Text from the command line on OSX](https://gist.github.com/martinbuberl/5823ed247d279d1a2d06)
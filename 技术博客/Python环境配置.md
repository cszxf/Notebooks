000-Python环境配置

# 一、anaconda

## 基础

[Anaconda安装](https://blog.csdn.net/ha_ha_ha233/article/details/87475799)

 [conda和pip比较](http://www.360doc.com/content/18/1209/11/11881101_800396689.shtml)

创建Python虚拟环境:

 使用 conda create -n your_env_name python=X.X（2.7、3.6等） anaconda 命令创建python版本为X.X、名字为your_env_name的虚拟环境。your_env_name文件可以在Anaconda安装目录envs文件下找到。

 `conda create -n cs python=3.7`

## 常用功能代码

[conda 创建/删除/重命名 环境](https://www.jianshu.com/p/7265011ba3f2)

 查看已有环境 `conda env list`



 切换环境

windows: `conda activate xxx(env name)` 
linux: `source activate xxx(env name)` 


查看当前环境安装包 `conda list`

 查看包版本 

```
conda list PackageName
```

复制环境

```
conda create -n NEWNAME --clone OLDNAME
```

删除环境

conda remove -n NAME --all

卸载安装包

```Shell
conda uninstall XXX

conda remove XXX

pip uninstall  XXX
```

 [更新卸载制定包](https://blog.csdn.net/wanttifa/article/details/92845377)

## pip

卸载第三方库 `pip uninstall torch` 

 

# 二、virtualenv

[python虚拟环境： conda create与 virtualenv对比](https://blog.csdn.net/weixin_41521681/article/details/98070414)

1、安装virtualenv

pip install virtualenv

2.创建虚拟环境

$ mkdir myproject

$ cd myproject

$ virtualenv venv

创建了一个名为myproject的文件夹，然后这里边创建虚拟环境venv。

 

在创建virtualenv时增加--no-site-packages 选项的virtualenv就不会读取系统包，如下：

 

virtualenv nowamagic_venv --no-site-packages

--distribute选项使virtualenv使用新的基于发行版的包管理系统而不是 setuptools 获得的包。 你现在需要知道的就是 --distribute 选项会自动在新的虚拟环境中安装 pip ，这样就不需要手动安装了。 当你成为一个更有经验的Python开发者，你就会明白其中细节。

 

virtualenv --distribute nowamagic_venv

3.激活虚拟环境

Linux:$ . venv/bin/activate或者source $ENV_BASE_DIR/$ENVIRONMENT_NAME/bin/activate

没有实验，所以暂时写两种方法，如果此时进入到venv虚拟环境文件夹下，可以source bin/activate

Windows:$ venv\scripts\activate

4.退出环境

```
deactivate
```

 

 
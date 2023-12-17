### pyinstaller暂不支持打包pyecharts，因此要解决此问题，可以有以下两种方法

1. ##### 使用打包多个文件的方式，直接把python安装的pyecharts(Lib\site-packages\pyecharts)贴到此exe所在的路径下

2. ##### 打包成单文件的形式（即只生成一个exe文件），手动--add-data添加所需资源进行打包，//用法：pyinstaller x.py --add-data "源地址;目标地址"。（目标的文件夹不存在会自动创建)

>比如pyecharts是安装在D:\langs_py目录下，运行以下打包命令
>
>pyinstaller -F -w -i aaa.ico  .\index.py --add-data D:\langs_py\Lib\site-packages\pyecharts:pyecharts
### pyinstaller暂不支持打包pyecharts，因此要解决此问题，可以有以下两种方法

1. ##### 使用打包多个文件的方式，直接把python安装的pyecharts(Lib\site-packages\pyecharts)贴到此exe所在的路径下

2. ##### 打包成单文件的形式（即只生成一个exe文件），手动--add-data添加所需资源进行打包，//用法：pyinstaller x.py --add-data "源地址;目标地址"。（目标的文件夹不存在会自动创建)

>比如pyecharts是安装在D:\langs_py目录下，运行以下打包命令
>
>pyinstaller -F -w -i aaa.ico  .\index.py --add-data D:\langs_py\Lib\site-packages\pyecharts:pyecharts
>
>3. 如果项目中引用了图片，可以用下面的方式引用图片的地址，这样打包后才能访问到图片
>
>   ```python
>   current_dir = os.path.dirname(os.path.abspath(__file__)) # 获取当前文件所在目录路径
>   self.ui.LoadingAnimation = LoadingAnimation(os.path.join(current_dir, 'gif', 'loading1.gif'))
>   ```
>
>   要把图片打包进exe中，可以有两种方式，1是修改spec文件中的datas,例如要把pyecharts和目录名为gif中的图片打包进去，可以这样写
>
>   ```python
>   datas=[('D:\\pythons\\duty\\venv\\Lib\\site-packages\\pyecharts', 'pyecharts'), ('D:\\pythons\\duty\\gif', 'gif')]
>   ```

​	2是在终端中输入命令：

pyinstaller --noconfirm --onefile --windowed --icon "D:/pythons/duty/pro.ico" --add-data "D:/pythons/duty/venv/Lib/site-packages/pyecharts;pyecharts/" --add-data "D:/pythons/duty/gif;gif/"  "D:/pythons/duty/main.py"

​	
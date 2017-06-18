## Yande.re图片爬虫

### 前言
每天打开电脑第一件事，就是打开[Y站](https://yande.re/post)，看看又更新了哪些图片、其中又有哪些适合作为壁纸

日久天长，总会感觉浪费时间精力，每天都要在一堆图片里找PC壁纸

这可不符合我作为一个码农的身份

正好最近想学学`Python3`，于是一边看着[廖学峰的Python教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)一边撸出来这个项目。写得很差，轻喷

本项目基于`Win7`、`Python3.5.2`开发，其他环境下未测试

### 功能
- 支持从指定的**开始页码**爬取到**结束页码**
- 也支持从**第一页**爬取到**上一次开始爬取的位置**
- 支持设置爬取的**图片类型**（全部、横图、竖图、正方形）
- 支持最大或最小**图片尺寸**、**宽高比**限制
- 按照当天的日期创建目录并存放爬取的图片
- 爬取结束后会在图片目录下生成日志文件

### 如何使用
**必须** 编辑`Function.py`第`5`行，将该变量的值设为自己想要的目录，程序将会自动创建，路径必须以斜杠结尾

- **方案一**：如果想要从**开始页码**爬到**结束页码**，请修改`index.py`第`12`行和第`15`行的两个变量；
- **方案二**：如果想要从**开始页码**爬取到**上一次开始爬取的位置**，请修改`index.py`第`15`行的值为`0`。还有`last_start_id.data`的内容，改为某张图片的id即可。爬到此图片时程序将停止。该方案下推荐将**开始页码**设为`1`，相当于每次执行都只从新增的图片中爬取 

> 例如某图片的详情页Url为：`https://yande.re/post/show/346737`，则图片id为`346737`

然后命令行执行`python index.py`即可（Windows下）。Linux下可直接执行

### 注意事项

值得一提的是，无论使用哪种方案运行，`last_start_id.data`的内容都会被自动修改为爬取到的第一张图片的id

这样做的目的是为了实现**方案二**，相当于每次执行都只从新增的图片中爬取。比较适合设置为自动运行之类的

### 更新日志
#### 1.0
终于完成了啦


######Lines above are written by mokeyjay######
######Lines below are written by chino######


Optimization points(WIP):
1.Log to file feature
2.Automatically limit the number of objects on crawl list to 60000(1500 pages)
3.Stability improvement(by using service feature on linux)
4.Intergration with my future app

All commits are welcomed!

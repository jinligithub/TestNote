###  1.什么是Selenium？
概念： Selenium是一个用于Web应用程序测试的工具；中文的意思（硒）
#### 1.1 Selenium特点
1. 开源软件：源代码开放可以根据需要来增加工具的某些功能
2. 跨平台：linux 、windows 、mac
3. 核心功能：就是可以在多个浏览器上进行自动化测试
4. 成熟稳定：目前已经被google , 百度， 腾讯等公司广泛使用
5. 功能强大：能够实现类似商业工具的大部分功能，因为开源性，可实现定制化功能
  4.1 Selenium 2.0


#### 1.2为什么要学习Selenium IDE
1. 可以使用Selenium IDE录制脚本，体验自动化脚本
2. 使用Selenium IDE录制的脚本转换为代码语言

### 2.安装Selenium IDE
1. 官网安装
2. 附加组件安装：我选择的火狐版本是35，可以直接在火狐浏览器的插件管理里面查找Selenium IDE，点击添加插件就好了
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726091614190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
3. 离线安装：把下载好的插件直接拖入浏览器就可以直接安装了
#### 2.1Selenium IDE运行
1.  Ctrl+Alt+S
2.  工具栏——>Selenium IDE
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726101137825.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
#### 2.3Selenium IDE的参数说明
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726101051123.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
1. 文件：创建、打开和保存测试案例和测试案例集。编辑：复制、粘贴、删除、撤销和选择测试案例中的所有命令。Options : 用于设置seleniunm IDE。
2. 用来填写被测网站的地址。
3. 速度控制：控制案例的运行速度。
4. 运行所有：运行一个测试案例集中的所有案例。
5. 运行：运行当前选定的测试案例。
6. 暂停/恢复：暂停和恢复测试案例执行。
7. 单步：可以运行一个案例中的一行命令。
8. 录制：点击之后，开始记录你对浏览器的操作。
9. 案例集列表。
10. 测试脚本；table标签：用表格形式展现命令及参数。source标签：用原始方式展现，默认是HTML语言格式，也可以用其他语言展示。
11. 查看脚本运行通过/失败的个数。
12. 当选中前命令对应参数。
13. 日志/参考/UI元素/Rollup 

**小Tips**：注意因为在播放脚本的时候会打开新的窗口，所以要把火狐浏览器的组织弹出新的窗口关闭，否则会报[warn] Link has target '_blank', which is not supported in Selenium! Randomizing target to be: selenium_blank30051错误
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726105128285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
录制的脚本保存之后是一个HTML页面，打开之后是一个表格，如下图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726105937259.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
**重点说明**：
1. id=kw：为百度搜索文本框id属性和值
2. id=su: 为百度一下按钮id属性和值 
#### 2.4定义调试插件 ：FireBug
 * FireBug插件是火狐浏览器一款插件，能够调试所有网站语言，同时也可以快速定位HTML页面中的元素；
  * 可以在插件管理里面查找Firebug，或者去网上找关于firebug的插在下载好了直接拖入火狐浏览器就行。
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726103234361.png)
* **作用**：定位元素(获取元素定位和查看元素属性)，即`快速查找一个元素标签的属性和值`
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726103830909.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
##### 注意事项
1. 录制：录制时红色录制按钮一定要打开->按下状态
2. 回放：由于网络延迟原因-建议选择最低
3. 浏览器：回放时浏览器要保持打开状态（否则点击回放，脚本无响应） 
4. 录制脚本时候是录制鼠标和键盘的所有在浏览器操作，那么脚本会出现多余的步骤，有时候我们需要手动填写脚本或修改脚本,所有我们有必要对Selenium IDE脚本编辑与操作有所了解

###  3.Selenium IDE脚本编辑与操作
**目的**：手动修改或编写脚本（采用录制方式很容易记录出多余的操作）

###### 3.1 编辑一行命令
在Table标签下选中某一行命令，命令由command、Target、value三部分组成。可以对这三部分内容那进行编辑。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726111722207.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 3.2 插入命令
在某一条命令上右击，选择“insert new command”命令，就可以插入一个空白，然后对空白行进程编辑
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726111800481.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726111837318.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 3.3 插入注释
鼠标右击选择“insert new comment”命令插入注解空白行，本行内容不被执行，可以帮助我们更好的理解脚本，插入的内容以紫色字体显示。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726111949653.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726112032215.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 3.4 移动命令
有时我们需要移动某行命令的顺序，我们只需要左击鼠标拖动到相应的位置即可。
###### 3.5 删除命令
选择单个或多个命令，然后点击鼠标右键选择“Delete”
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726112129669.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 3.6 命令执行
选定要执行的命令点击单个执行按钮即可，注意：有一些命令必须依赖于前面命令的运行结果才能成功执行，否则会导致执行失败。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726112216161.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)

### 4. Selenium IDE常用命令
###### 4.1 open(url)命令
作用：打开指定的URL，URL可以为相对或是绝对URL；
Target：要打开的URL；value值为空
  1. 当Target为空，将打开Base URL中填写的页面；
  2. 相对路径： 当Target不为空且值为相对路径，将打开Base URL + Target页面。如，假设Base URL为http://www.zhi97.com，而Target为/about.aspx，则执行open命令时，将打开http://www.zhi97.com/about.aspx
  3. 绝对路径： 当Target以http://开头时，将忽略Base URL，直接打开Target的网址，
  4. 以http或https开头的为绝对路径，否则为相对路径
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726112604758.png)
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726112633206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 4.2 pause(waitTime)
**作用**：暂停脚本运行
**waitTime**：等待时间，单位：ms；//Target=1000
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726113129532.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 4.3 goBack()
**作用**：模拟单击浏览器的后退按钮；
**提示**：由于没有参数，所以Target和Value可不填，（`注意：必须是同一个窗口代开两个以上的url才可以）；`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726113337199.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726113813824.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 4.4 refresh()
**作用**：刷新当前页；
**提示**：由于没有参数，所以Target和Value可不填；
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726113843492.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 4.5 click(locator)
**作用**：单击一个链接、按钮、复选框或单选按钮；
**提示**：如果该单击事件导致新的页面加载，命令将会加上后缀“AndWait”，即“clickAnd Wait”，或“waitForPageToLoad”命令；

###### 4.6 type(locator,value)
**作用**：向指定输入域中输入指定值；也可为下拉框、复选框和单选框按钮赋值.
**Target**：元素的定位表达式；
**Value**：要输入的值；
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726114451790.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
###### 4.7 close()
**作用**：模拟用户单击窗口上的关闭按钮（关闭当前窗口）；
**提示：**由于没有参数，所以Target和Value可不填；
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190726114546445.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
5. 总结
6. 为什么学习Selenium IDE插件工具
7. Selenium安装、启动方式
8. FireBug作用
9. Selenium IDE常用命令
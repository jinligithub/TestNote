### 1.认识Jmeter
1. Apache JMeter是Apache组织开发的基于Java的压力测试工具。用于对软件做压力测试，它最初被设计用于Web应用测试，但后来扩展到其他测试领域。 

2. 它可以用于测试静态和动态资源，例如静态文件、Java 小服务程序、CGI 脚本、Java 对象、数据库、FTP 服务器 等等进行性能测试。JMeter 可以用于对服务器、网络或对象模拟巨大的负载来测试他们的强度，分析来自不同压力类别下测试它们的强度和分析整体性能可以使用它做性能的图形分析或在大并发负载测试你的服务器/脚本/对象。

3. JMeter能够对应用程序做功能/回归测试，通过创建带有断言的脚本来验证你的程序返回了你期望的结果。为了最大限度的灵活性，JMeter允许使用正则表达式创建断言。

**注意**：CGI是Common Gateway Interface的缩写，是用于连接主页和应用程序的接口。是在WebServer端运行的一个可执行程序，由主页的一个热链接激活进行调用，并对该程序的返回结果进行处理，显示在主页上。简而言之，CGI就是为了扩展主页的功能而设立的。

### 2.Jmeter的作用及其特点
#### 2.1Jmeter的作用
1. 接口测试 
2. 性能测试 
3. 压力测试 
4. Web自动化测试 
5. 数据库测试 
6. JAVA程序测试
#### 2.2Jmeter的优点
1. 开源、免费
2. 支持多协议
3. 小巧
4. 功能强大
#### 2.3Jmeter的缺点
1. 不支持IP欺骗
2. 使用JMeter无法验证JS程序，也无法验证页面UI，所以要须要和Selenium配合来完成
  Web2.0应用的测试

### 3.Jmeter的下载安装
#### 3.1下载
下载地址：http://jmeter.apache.org/download_jmeter.cgi

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805145217706.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
#### 3.2 安装：
1. 把下载好的软件安装包解压到磁盘里面
2. 配置Jmeter的环境变量
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805145637681.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805145705242.png)
3. 在Windows下进入命令行输入jmeter检测是否安装成功
#### 3.3 Jmeter的启动方式
1. 在命令行输入jmeter，启动
2. 双击Jmeter.bat启动
    *  出现Jmeter不是内部或外部命令在环境变量PATH中添加Jmeter路径bin目录，
      比如（E:\测试\Tools\apache-jmeter-3.1\bin）
3. 双击 ApacheJMeter.jar文件
### 4.Jmeter常用的目录说明
#### 4.1Bin目录
存放可执行文件和配置文件
* Jmeter.bat：windows系统中JMeter的启动文件
* ApacheJMeter.jar Java环境下的JMeter启动文件
* Jmeter.log：日志文件
* Jmeter.sh：linux系统中JMeter的启动文件
* Jmeter.properties：系统配置文件
* Jmeter-server.bat：windows分布式测试要用到的服务器配置
* Jmeter-serve：linux分布式测试要用到的服务器配置

```java
其中系统配置文件中的SSL设置重点关注如下几个：
# 指定HTTPS协议层
https.default.protocol=TLS
# 指定SSL版本
https.default.protocol=SSLv3
# 设置启动的协议
https.socket.protocols=SSLv2Hello SSLv3 TLSv1
# 缓存控制，控制SSL是否可以在多个迭代中重用
https.use.cached.ssl.context=true
```
#### 4.2 docs目录(了解开源)
* docs：是JMeter的java Doc，可打开api\index.html页面来查看;

#### 4.3 extras目录
* 扩展插件目录。
- 提供了对Ant的支持，可以使用Ant来实现自动化测试，例如批量脚本执行，产生html格式的报表，测试运行时，可以把测试数据记录下来，jmeter会自动生成一个.jtl文件，将该文件放到extras目录下，运行"ant -Dtest=文件名 report"，就可以生成测试统计报表。


#### 4.4 lib目录
* 所用到的插件目录，里面均为jar包。
* jmeter会自动在jmeter_HOME/lib和ext目录下寻找需要的类，lib下存放JMeter所依赖的外部jar：如httpclient.jar、httpcore.jar、httpmime.jar等等。

* 其中lib\ext目录下存放有Jmeter依赖的核心jar包，ApacheJMeter_core.jar、ApacheJMeter_java.jar在写client端需要引用，JMeter插件包也在此目录下。

* lib\junit下存放junit测试脚本.

**注意**：如果在 Jmeter 中运行脚本时报如下错误：即发生 java.lang.NOClassDefFoundError 的错误，都是因为缺少依赖的 jar 造成的
#### 4.5 Licenses目录
* jmeter证书目录
#### 4.6  printable_docs目录
* 用户使用手册
* printable_docs的usermanual子目录下的内容是JMeter的用户手册文档，其中usermanual
  下component_reference.html是最常用到的核心元件帮助文档。

### 5 .Jmeter的参数说明
#### 5.1添加测试计划
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805154926411.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)


#### 5.2 添加线程组
右键点击 测试计划--->添加--->Threads(users)--->线程组，就可以成功添加一个线程组了。
1. 属性说明
   * 线程数：虚拟用户数
   * Ramp-Up Period(in serconds)：启动虚拟全部用户数所需要的时间
   * 循环次数 ：指定次数或勾线永远
   * 调度器：勾选后，调度器配置才能使用；
2. 调度器配置
   * 持续时间（秒）：设置脚本压测持续时间
   * 启动延迟（秒）：启动延迟时间

Jmeter中最重要的就是线程组了，线程组就相当于用户活动，一个线程组就相当于有一个用户活动，添加多个线程组就相当于模拟多个用户活动对服务器进行测试。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805155715759.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
另一个循环控制器的设置：
 右键点击线程组--->添加---->逻辑控制器--->循环控制器，这里也是针对线程组循环的功能
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805155940285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
**注意**：关于线程组界面和循环控制器界面，这两个循环控制，以后者为主要生效。
* 比如说你再线程组里面勾选了循环次数是永远，线程数是2,；循环控制器写的次数是2，那么只会运行2X2=4次，以循环控制器的循环次数为准；
* 假如你的线程组循环次数写的是2，线程组是2，循环控制器写的次数是永远，那么会一直循环下去，还是以循环控制器的设置为主。


#### 5.3 HTTP请求的参数详解
1. **名称**：本属性用于标识一个取样器，建议使用一个有意义的名称。
 2. **服务器名称或IP** ：HTTP请求发送的目标服务器名称或IP地址。
 3. **端口号**：目标服务器的端口号，默认值为80 。
 4. **协议**：向目标服务器发送HTTP请求时的协议,可以是http或者是https ,默认值为http 。
 5. **方法**：发送HTTP请求的方法，可用方法包括GET、POST、PUT、DELETE。
 6. **Content encoding** ：内容的编码方式，默认值为iso8859；一般设置【UTF-8】
 7. **路径**：目标URL路径（不包括服务器地址和端口）
 8. **同请求一起发送参数**:请求时需要传递参数，如：对某个资源list查询
     http://127.0.0.1:8000/api/departments/?\$dep_id_list=T01,T02,T03
      参数名称：【\$dep_id_list】
      参数值：T01,T02,T03
 9. 消息数据体的作用（BodyData）:
   * 新增或更新时需要传递JSON报文；如学院新增是的JSON报文填写位置：

```java 
 {
 		"data": [
 					{
						 "dep_id": "T01",
						 "dep_name": "Test学院",
						 "master_name": "Test-Master",
						 "slogan": "Here is Slogan"
					 }
		     ]
  }
```
* 2. 【注意】：新增和更新时传入报文也需要设置Content-Type:application/json 告诉服务器我传的数据格式为JSON格式； 
      **设置地点**：配置元件-->HTTP信息头管理器
      ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190805153745909.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwOTU1ODI0,size_16,color_FFFFFF,t_70)
##### HTTP请求总结：
  1. 接口完整请求地址
  2. JSON报文存放地址
  3. 设置默认请求数据格式
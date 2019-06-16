博客里面有图片 会比这清除： <https://blog.csdn.net/qq_40955824/article/details/92397697>

##### sonarqube的介绍

sonarqube主要用于代码静态分析,用于检查代码是否存在存在的格式,bug,安全漏洞问题,同时也提供了复杂度,代码 行数等质量度量数据.

代码静态分析（Program Static Analysis）是指在不运行代码的方式下，通过词法分析、语法分析、控制流、数据流分析等技术对程序代码进行扫描，验证代码是否满足规范性、安全性、可靠性、可维护性等指标的一种代码分析技术


##### sonarqube使用的场景
开发代码中实时检查：可以装插件，然后根据自己指定的规则对代码进行扫描，然后就会实时反馈代码里面的问题。
优点：可以快速发现问题和解决问题，

开发代码完毕，提交代码到配置库之后，定期或者不定期扫描，
缺点：它是在代码开发完成之后才进行扫描，任务量大，此时发现问题和修改问题的成本就会变得的很大


##### SonarQube的特性
```
1、易于安装，开箱即可启动

2、易于配置，所有配置可以通过其提供的web界面实现

3、可以与CI系统，例如jenkins完美集成

4、丰富的扫描规则，支持自定义，并可以集成findbugs,pmd,checkstyle等插件

5、丰富的格式支持，可以扫描java\js\xml\jsp等多种格式

6、丰富的统计功能，例如覆盖率，代码行数

7、支持违规的处理、分配等工作流，可以扫描的有问题的代码进行处理，

8、可以对违规进行确认，误报的违规一次确认后将不再统计在内，如果工具有误报，工具认为是bug，此时可以进行设置下次遇到同样的问题，工具就不会认为它是bug

9、支持maven\ant\命令行等方式扫描
```


##### sonarqube分为以下产品组：
```
sonarqube更新频繁，更新会导致一些插件的不可用
sonarqube：sonarqube是一个web平台，是sonarqube的基础，统一管理插件和规则，统一展现度量数据
SonarQube Scanners：命令行扫描工具，进行代码的静态扫描
SonarQube Plugins：插件，支持多种语言
SonarLint：IDE集成插件
```
##### 安装SonarQube（Linux下）
1.先从本地把软件包导入到服务器或者虚拟机上

2.解压sonarqube： 命令 unrar x sonarqube-6.4.rar

3.修改配置文件

修改端口号：vi xxx/sonarqube-6.4/conf/sonar.properties

注意：一半都使用的是默认端口号，如果默认的端口号被占用才需要去修改端口号，一般不要组修改端口号。

因为我的默认9000端口号没有被占用，所以不要修改。

4.启动sonarqube

在sonarqude的安装包的bin目录里的linux-x86-64下边有他的启动命令



可以使用该命令进入该目录： cd ./sonarqube-6.4/bin/ linux-x86-64/

启动sonarqube：  因为我是root权限所以我不用root命令

第一次启动：sudo ./sonar.sh start 

第二次启动：sudo ./sonar.sh restart 

查看sonarqube的状态：./sonar.sh status

必须要在: sonar.sh的路径下执行该命令，否则会显示找不到该文件：/sonarqube-6.4/bin/linux-x86-64


###### 出现问题：

1.输入命名后说我权限拒绝
解决方法：修改sonar.sh的文件权限

登录sonqrqube
注意：第一次的登录sonarqube他的账户和密码都是admin

###### sonarqube目录结构如下：
bin：启动、停止命令目录
conf：配置目录，可以配置端口、数据库等信息
data：数据存放目录，子目录es，web为缓存的数据目录，可以删除，删除后会自动生成。
extensions\plugins：插件存放目录，手工下载的插件需要放在该目录
lib：依赖jar
logs：日志文件
temp：临时文件目录，可以删除
web：web目录，不可以删除，开发语言为ruby
##### 安装插件sonarqube插件
1.在sonarqube的web页面进行插件的安装



2.如果web端安装插件失败可以在，Linux环境在安装插件。在sonarqube的目录下有一个扩展包文件extension文件里面有个plugins文件下装的就是插件，我们可以把自己的插件文件放入这个包下边，然后重新启动sonarqube使插件效




###### 安装sonarscanner
1.先把安装包导入本地服务器：
2.解压：unrar x sonar-scanner-cli-3.0.3.778-linux.rar
3.配置sonarscanner的环境变量（集成Jenkins需要配置）
命令：vi /etc/profile
SONAR_RUNNER_HOME=/root/sonar-scanner-cli-3.0.3.778-linux
PATH=$SONAR_RUNNER_HOME/bin:$PATH
export SONAR_RUNNER_HOME 
export PATH
执行source /etc/profile使/etc/profile生效


##### 练习一：sonarscanner扫描 
（此次测试采用的sonarqube默认的质量阀）

1.把自己的Java项目放入Linux环境下

2.在项目目录下，创建一个sonar-project-properties文件，来定义当前项目的自动化命令行扫描文件

扫描规则：
```
 工程关键字，整个系统中唯一,可修改，一般设为项目英文名
sonar.projectKey=sonar
#工程名,一般设为项目英文名
sonar.projectName=sonar
#工程版本号，可设置为项目的版本号
sonar.projectVersion=1.0
#工程存放目录,.表示当前路径，不用修改
sonar.projectBaseDir=. 
#设置扫描JAVA还是PLSQL，设为 JAVAmodule,PLSQLmodule则同时扫描两个
sonar.modules=JAVAmodule
#不进行扫描的文件
#sonar.exclusions=test/*.java,b.java
#JAVAmodule的工程名称,可修改
JAVAmodule.sonar.projectName=sonar_java
 JAVAmodule的扫描语言，不可修改
JAVAmodule.sonar.language=java
#源码存放目录，可设置为src,java等多个目录,.表示当前路径下所有文件
JAVAmodule.sonar.sources=.
#源码字符集，根据实际修改
JAVAmodule.sonar.sourceEncoding=UTF-8
#设置工程使用的JDK版本，需要修改，可能影响扫描结果
JAVAmodule.sonar.java.source=1.6
#工程存放路径，不用修改
JAVAmodule.sonar.projectBaseDir=.
#以下两项在编译后添加，部分安全规则需要二进制文件，这时需要设置以下两项
#编译后的二进制文件目录
#JAVAmodule.sonar.java.binaries=.
#依赖jar包目录
#JAVAmodule.sonar.java.libraries=.
#PLSQLmodule的工程名称,可修改
PLSQLmodule.sonar.projectName=sonar_plsql
PLSQLmodule.sonar.language=plsqlopen
#源码存放目录，可以逗号分隔填写多个目录
PLSQLmodule.sonar.sources=sql
PLSQLmodule.sonar.sourceEncoding=GBK
PLSQLmodule.sonar.projectBaseDir=.
```

扫描规则制定为，然后执行：

1.执行代码:   sudo /root/sonar-scanner-3.0.3.778-linux/bin/sonar-scanner
2.以debug模式执行代码:   sudo /root/sonar-scanner-3.0.3.778-linux/bin/sonar-scanner-debug
3.在命令行扫描完成之后会在sonarqube的web端有一个扫描结果分析，里面有代码的覆盖率，重复率，多少个bug，多少个漏洞等等



###### 2.自己创建质量阀
1）.创建质量阀
2）.添加质量阀和
3）.勾选测试的项目，然后测试时质量阀就会应用到该项目上面去
4）.质量配置
激活更多的质量规则
到这里质量阀就将好了，他就可以应用到项目里


#### jenkins和sonarqube集成

启动jenkins的最简单指令：
nohup java -jar jenkins.war --httpPort=80

###### 1.-如何把jenkins和sonarqube关联起来

1）在jenkins里面有一个sonarqube的插件

2）在全局工具配置里面进行配置

配置sonarscanner插件的加路径

3）在系统设置里面配置sonarqube的服务器

首先在sonarqube里面创建sonarqube服务器的指令令牌

配置sonarqube的服务器指令令牌

此时jenkins和sonarqube就建立了联系

4)在jenkins里面的构建里查看是否有sonarqube
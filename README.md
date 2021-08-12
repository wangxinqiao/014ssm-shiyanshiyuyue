#  006ssh实验室预约管理系统
006ssh实验室预约管理系统


## 环境要求
IDEA开发环境，Spring,springMvc,Mybatis框架，前端Jsp技术，AJax技术，使用Mysql 5.7 数据库。本项目非Maven项目；

## 数据导入：
````
在MySQL数据库中创建数据库，数据库名称建议为laboratory(可自定义),导入lrms.sql；
数据库创建并导入完成后，在ApplicationContext.xml文件中配置数据库名称及用户名密码等；
````
## 运行
````
运行成功后，在浏览器中访问http://localhost:8080/；
管理员账号：admin  密码：123456
教师账号：Z0000001 密码：js123456
学生账号：1309030223 密码：xs123456
````
演示视频：[ **点此查看** ](https://www.bilibili.com/video/BV18b4y1d7Vi/)
源码获取：[ **点此获取** ](http://www.shuyue.fun/index.php?type=productinfo&id=117)

## 功能介绍
本系统的用户可以分为三种：管理员、教师、学生。以下针对三种用户分别描述其功能需求。
## 1.管理员功能需求描述
以下是管理员的功能需求：

（1） 登录：管理员在登录界面输入自己的账号密码(默认是：gly123)后，即可登录系统进行相关的操作。

（2） 管理用户：管理员可以管理用户信息。查看用户、删除用户。

（3） 重置密码

（4） 发布公告：发布重要通知,用户登录系统之后即可看到公告列表。

（5） 管理实验室：管理员可以管理实验室信息。新增、修改、删除（包括名称、地点、设备台数(即总人数)等）。

备注：由于显示默认的排期表需要，id为1的实验室永久不可删除。

（6） 查看实验室预约情况：管理员可以查看所有预约信息 如实验室是否被预约，被谁预约，预约时间，预约人数等。

（7） 高级搜索：管理员输入搜索关键字（如实验室地点，预约区间，预约用户），即可查看详细的预约情况。

（8） 查看排期表：选择某个实验室，可以查看其未来15天每天仍可被预约的人数。

（9） 退出登录
## 2.教师功能需求描述
以下是教师的功能需求：
备注：该系统用户不可以注册，只能由运维人员在数据库中添加用户，这样可以避免校外人士注册该系统造成不必要的资源浪费。
教师无需注册，系统默认与其他教学系统的数据库连接，默认用户名为教职工号，密码为“js123456”，教师第一次登陆之后重置密码可以保证用户权限。

（1） 登录：教师在初始界面输入职工号，密码，即可登录预约系统进行后续操作

（2） 重置密码

（3） 查看公告：登陆成功后在系统主界面可以查看管理员发布的所有公告，公告列按照创建时间倒序排列。

（4） 查看个人信息：教师可以查看个人信息（用户名、学院、专业等）

（5） 查看实验室列表：教师可以查看实验室的详细信息

（6） 预约：分为个人预约和课堂预约

个人预约：教师选择实验室，选择日期，选择时间区间，选择人数即可。此时最多可以预约10个位置,且该实验室剩余的位置还可以被其他学生预约,但是不能被课堂预约。

课堂预约：教师选择预约日期段，选择每周几，选择预约时间段、指定课堂、输入相应的描述信息即可完成预约。此时无论实验室是否被预约满，该时间段都不可以被再预约。

（7） 查看排期表：选择某个实验室，可以查看其未来15天每天仍可被预约的人数。

（8） 高级搜索：教师输入搜索关键字（如实验室地点，预约区间，选择预约类别，选择课堂），即可查看详细的预约情况。

（9） 管理预约信息：教师可以查看自己预约的信息、可取消预约 前提是预约日期是当天之后。
注：已经超出预约时间的预约信息不能删除

（10） 管理课堂信息：教师可以新增、修改、删除课堂信息。
注：该课堂若已经存在，不可再次添加。

（11） 导入导出学生名册：教师可以针对某一课堂导入导出学生名册，但是要按照固定的excel模板。

（12） 发布课堂任务：教师可以针对某一课堂发布任务，该课堂的学生可以看到该课堂作业通知信息

（13） 上传文件：教师可以上传实验资料等

（14） 查看学生作业：教师可以下载或者在线预览学生实验报告

（15） 评分和评价

（16） 退出登录
## 3.学生功能需求描述
学生的功能需求主要包括以下几种：
备注：学生无需注册，系统默认与其他教学系统的数据库连接，默认用户名为学号，密码为“xs123456”，学生第一次登陆之后重置密码即可以保证用户权限。

（1） 登录

（2） 重置密码：当学生忘记密码或者想要重置密码，可以重置自己的密码。

（3） 查看公告：登陆成功后在系统主界面可以查看管理员发布的所有公告，公告列按照创建时间倒序排列。

（4） 查看个人信息：学生可以查看个人信息（用户名、学院、专业等）

（5） 查看实验室列表：学生可以查看实验室的详细信息

（6） 预约：默认是个人预约，学生不能进行课堂预约
个人预约：学生选择实验室，选择日期，时间区间，选择人数即可。此时最多可以预约10个位置,且该实验室剩余的位置还可以被其他学生预约,但是不能被课堂预约。

（7） 查看排期表：选择某个实验室，可以查看其未来15天每天仍可被预约的人数。

（8） 管理预约信息：学生可以查看自己预约的信息、可取消预约 前提是预约日期是当天之后。
注：已经超出预约时间的预约信息不能删除
学生还可以查看所在课堂的预约信息，只能看到课堂名称、预约日期、预约区间，此时不能取消预约，只能由该课堂的教师取消预约。

（9） 高级搜索：学生输入搜索关键字（如实验室地点，预约区间，选择课堂），即可查看详细的预约情况。

（10） 查看课堂任务：若学生的课程A预约了实验室，则教师A发布课堂任务后，学生可以看到任务，若没有预约则看不到公告

（11） 上传实验报告：前提是课程A已预约实验室，可以上传文件并且可以写说明

（12） 下载实验报告：可以下载以及上传的实验报告

（13） 查看分数：每次上传作业之后，可以看到教师的评语和分数以及期末总的实验分数

（14） 退出登录

## 运行截图

![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/095522_3cf76eb9_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/095531_51ea19b2_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110455_f087856f_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110521_8312646d_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110534_87bf7345_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110532_a6874950_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110547_892578b7_863230.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/0317/110558_9e78c974_863230.png "屏幕截图.png")

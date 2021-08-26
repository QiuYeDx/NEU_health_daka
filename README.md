### python（本地无python环境也ok）脚本进行NEU健康、体温打卡，腾讯云云函数定时调用脚本，以防万一，打卡失败时qq邮箱通知。

## PS:该版本已在python3.9 pycharmIDE中测试通过 by QiuYeDx

# 使用流程：

## 1、打卡配置
下载所有文件

在 config.py 文件中填写需要打卡的学号与密码

![1.png](https://z3.ax1x.com/2021/08/08/f1pyTK.png)
## 2、通知邮箱配置（可选）
开启qq邮箱SMTP服务，得到授权码：[参考博客](https://www.cnblogs.com/Alear/p/11594932.html)

在 config.py 文件中配置邮箱信息。
之后可直接运行sendEmail.py文件测试发送效果。

## 3、服务器部署
将源文件上传至服务器，然后设定8:00、13:00、18:00的系统计划任务即可。
以linux为例:
''' crontab -l  #查看当前计划任务
crontab -e  #修改系统计划任务
'''
选择自己常用的编辑器后，在文末添加以下语句：
''' 0 8 * * * python3 /.../run.py
0 13 * * * python3 /.../run.py
0 18 * * * python3 /.../run.py
‘’‘
搞定。
## 该版本已为挂在自己的服务器使用做了一些定制，不能直接挂在腾讯云上。[原版链接](https://github.com/Bmaili/NEU_health_daka)，[原作者Bmaili](https://github.com/Bmaili)  by QiuYeDx

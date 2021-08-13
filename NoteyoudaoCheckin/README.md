# NoteYoudaoCheckin
### 有道云笔记签到<br>
### 推荐使用本地在VPS上面跑(如果不想每天微信都弹登录提醒的话
### 腾讯云函数跑的话每次都会进行登录,而本地首先读cookie再使用账号密码登录,cookie有效期挺短的<br>
### Github Actions的话没试过，可能会异地登录，需要进行验证啥的
### 使用方法<br>
VPS/本地使用<br>
1.测试环境为python3.7.9,自行安装python3<br>
2.requirements.txt 是所需第三方模块，执行 `pip install -r requirements.txt` 安装模块<br>
3.在脚本内直接修改"note_username"(str)为登录账号,"note_password"(str)为登录密码,"SCKEY(可选)"为Server酱推送<br>
   或者添加系统环境变量变量名为"note_username"和"note_password"，值为账号和密码<br>
4.Python 和需要模块都装好了直接在目录 cmd 运行所要运行的脚本。<br>
5.每天定时：Windows定时可以使用自带的"任务计划程序"，Linux的话可以使用cron等。<br>
<br>
Github Actions版本<br>
自行探索<br>
<br>
[腾讯云函数SCF](https://console.cloud.tencent.com/scf/index)的版本<br>
1.下载requirements.zip所需库，到[层](https://console.cloud.tencent.com/scf/layer)里面新建一个层<br>
2.到[函数服务](https://console.cloud.tencent.com/scf/list)里面新建一个函数，使用自定义创建，输入名字，运行环境选择python3.6<br>
3.修改执行方法为index.main，修改index.py文件，把SCF版py文件内容覆盖掉里面的函数<br>
4.高级设置，添加多个环境变量key内输入：1.note_username 2.note_password 3.推送服务设置值(可选)<br>
value内输入：1.登录账号 2.登录密码 3.推送服务设置值(可选)<br>
5.层配置，添加层，选择刚才新建的层。最后点完成<br>
6.进入函数→触发管理→新建触发器，按自己需求定时启动<br>
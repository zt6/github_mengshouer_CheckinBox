# Cloud189Checkin
天翼云盘每日签到一次，抽奖2次(抽奖地址已失效)<br>
使用方法<br>
1.测试环境为python3.7.6,自行安装python3<br>
2.requirements.txt 是所需第三方模块，执行 `pip install -r requirements.txt` 安装模块<br>
3.可在脚本内直接填写账号密码<br>
4.Python 和需要模块都装好了直接在目录 cmd 运行所要运行的脚本。<br>
<br>
Github Actions版本<br>
自行探索<br>
<br>
<br>
[腾讯云函数SCF](https://console.cloud.tencent.com/scf/index)的版本<br>
1.下载requirements.zip所需库，到[层](https://console.cloud.tencent.com/scf/layer)里面新建一个层<br>
2.到[函数服务](https://console.cloud.tencent.com/scf/list)里面新建一个函数，使用自定义创建，输入名字，运行环境选择python3.6<br>
3.修改执行方法为index.C189Checkin，修改index.py文件，把SCF版py文件内容覆盖掉里面的函数<br>
4.高级设置，添加多个环境变量key内输入：1.username 2.password 3.推送服务设置值(可选)<br>
value内输入：1.登录手机号 2.登录密码 3.推送服务设置值,报错提醒<br>
5.层配置，添加层，选择刚才新建的层。最后点完成<br>
6.进入函数→触发管理→新建触发器，按自己需求定时启动<br>


登录看的以下项目：
> [Cloud189](https://github.com/Dawnnnnnn/Cloud189)
> [cloud189](https://github.com/Aruelius/cloud189)

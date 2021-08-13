# PT-Tools
### NexusPHP的大部分PT站点通用签到<br>
NexusPHP的PT站点少部分站点会自己改网页，这部分自求多福.jpg
### 使用方法<br>
Github Actions版本<br>
自行探索<br>
<br>
[腾讯云函数SCF](https://console.cloud.tencent.com/scf/index)的版本<br>
1.下载requirements.zip所需库，到[层](https://console.cloud.tencent.com/scf/layer)里面新建一个层<br>
2.到[函数服务](https://console.cloud.tencent.com/scf/list)里面新建一个函数，使用自定义创建，输入名字，运行环境选择python3.6，下一步<br>
3.修改index.py文件，复制仓库脚本内容覆盖原来的index.py
4.高级设置，添加多个环境变量key内输入：1.pt_website 2.cookie_pt 3.推送服务设置值(可选)<br>
value内输入：1.需要签到的PT站点(例如https://xxx.xxx/index.php) 2.获取到的cookie 3.推送服务设置值(可选)<br>
5.层配置，添加层，选择刚才新建的层。最后点完成<br>
6.进入函数→触发管理→新建触发器，按自己需求定时启动<br>

### Cookie获取方法<br>
浏览器打开需要签到的网站并登录，F12打开检查<br>
在 Chrome 浏览器下方的开发工具中单击 Network 标签页(其他浏览器大同小异)<br>
F5刷新当前网站，随便选一个Name里面的网页，在右侧Headers内找到Cookie: xxxxxx，复制xxxx的东西，一般很长一大串<br>
Headers如果没有Cookie就换另一个Name里面的网页，实在看不懂就自行baidu吧.jpg<br>
Cookie过期就必须手动更换，再重复一次获取流程，然后Github到secrets里更新，腾讯云函数就到函数配置中修改环境变量的值

### ToDo<br>
1.投票 2.说谢谢
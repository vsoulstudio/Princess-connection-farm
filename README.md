# Princess connection 公主连结农场脚本v0.3

![](https://img.shields.io/badge/license-GPL--3.0-blue)![](https://img.shields.io/badge/opencv-2.0-blue)![](https://img.shields.io/badge/UIAutomator-2-blue)

## 简介

此项目为国服公主连结脚本，使用opencv图像识别进行按钮分析。本项目基于公主连接opencv高级脚本(https://github.com/bbpp222006/Princess-connection) 开发。

## 特点

- [x] 多线程多开 **new**
- [x] 39对1农场 **new**
- [x] 家园领取
- [x] 行会点赞
- [x] 自动捐赠
- [x] 地下城 农场/大号
- [x] 收取任务
- [x] 收取礼物
- [x] 免费扭蛋
- [x] 自动刷经验
- [x] 自动刷8/10/11图 可自定义每关扫荡次数
- [x] 自动购买体力
- [x] 自动探索(额外脚本)
- [x] 初始化mana号(额外脚本)

功能详解

1. 模拟器多开管理 ← new!!
2. 39对1农场管理 ← new!!
3. 账号批量登录/退出；
4. 收取所有礼物；
5. 检测行会捐赠请求并捐赠；
6. 地下城自动刷支援，默认第一个人，请确保支援角色不大于农场号等级+30；
7. 购买3次体力；
8. 收取所有任务报酬；
9. 刷全部8/10/11图 3次（请确保你的农场号已经全部3星通关）*次数在Automator.py中全局定义*；
10. 家园自动收取；
11. 公会给副会长（默认排序第二位）自动点赞；
12. 自动免费扭蛋；
13. 购买10次mana；
14. *自动刷经验关(1-1，内含自动购买体力)；
15. *自动刷完第三个地下城（断崖的遗迹）及自动探索（主程序中没有包含，为额外脚本）；
16. *购买70次mana（主程序中没有包含，为额外脚本）；
17. *初始化mana农场号，从0到3-1；

## 环境

需要安装下列python包:

```
pip install opencv-python==3.* -i https://pypi.tuna.tsinghua.edu.cn/simple/
pip install matplotlib -i https://pypi.tuna.tsinghua.edu.cn/simple/
pip install uiautomator2 -i https://mirrors.aliyun.com/pypi/simple/
```

若使用模拟器，则需要将模拟器设置为桥接模式，同时需要打开usb调试。具体参考这个项目(https://github.com/Jiahonzheng/JGM-Automator)

建议使用雷电模拟器，本项目中均以雷电模拟器为示例。

**重要：模拟器分辨率要求540*960**


## 使用方式

1. 在main.py中定制自己需要的功能，不需要的用#号注释，或直接跳过本步骤
2. 启动雷电模拟器，安装b服版公主连结，设置分辨率为540*960   **注意不是960 * 540**
3. 启动雷电多开器，用复制模拟器功能 根据电脑性能酌情多开
4. 然后在终端中输入

```
cd main.py文件所在的目录（自己复制）
例如：cd C:\Users\Administrator\Documents\Princess-connection-farm
```

5. 再输入

```
python main.py
```

**※**:为额外注释脚本，不会在main中运行。

**第二次使用只需**

1. 启动雷电多开器，多开复数个模拟器；
2. 然后在终端中输入

```
cd main.py文件所在的目录（自己复制）
例如：cd C:\Users\Administrator\Documents\Princess-connection-farm
```

3. 再输入

```
python main.py
```

## 额外说明

1. **本项目下zhanghao.txt为待刷账号与密码**;
   账号与密码之间用tab键或空格作为分割；

   不同账号之间按行分割；

   第一行的zhanghao mima请也改成自己的账号密码。

   下面为实例，标注图号的将进行刷图，不标注图号的不刷图
   
   ```
   zhanghao1    mima1   11
   zhanghao5    mima5   11
   zhanghao6    mima6
   zhanghao7    mima7
   ```
   
2. **本项目下40to1.py为39对1行会管理**，执行方法参照main.py；

   请在40_1.txt中输入行会1的农场号账号与密码（不包括会长）

   请在40_2.txt中输入行会2的农场号账号与密码（不包括会长）

   请在40_huizhang.txt中输入大号的账号、密码、UID，行会1会长的账号密码，行会2会长的账号密码

   ~~~
   大号账号	大号密码	大号UID
   行会1会长账号	密码
   行会2会长账号	 密码
   ~~~

3. **本项目下goumaimana.py为购买70次mana**，执行方法参照main.py

4. **本项目下juanzeng.py为行会捐赠装备**；
   
   该程序会读取zhanghao.txt中**标有图号**的账号，进行捐赠。没有标图号的认为是mana号不进行捐赠；

   建议每天上午跑一次main.py，8小时后请求新的装备后再跑juanzeng.py；

5. **本项目下dixiacheng.py为自动刷完第三个地下城（断崖的遗迹）及自动探索**；

   请在zhanghao2.txt中输入账号密码；

   请把”我的队伍“中1队设为打boss队，2队设为aoe队；

   探索默认打第5级；

6. **本项目下chushihua.py为自动完成从全新B站账号到3-1的农场号初始化功能**；

   请在zhanghao_init.txt中输入账号密码

   若需要多开，请保证自己的电脑能够高效率运行，或者请手动调高延时，否则会出现点不上的情况。有问题可以在群里反馈。

7. 一些剧情由于识别率问题需要手动跳过，例如公会之家的剧情。如果不想手动跳过，请在主程序尝试自行添加识别，或直接注释相关函数；

8. **刷图购买体力和刷经验是相冲的！！！**

9. 请不要用于商业用途。代码交流和bug反馈请加群加qq群 1130884619

   ![image](https://s1.ax1x.com/2020/06/26/NsXjh9.png)

10. 感谢CyiceK(https://github.com/1076472672) 、Dr-Bluemond(https://github.com/Dr-Bluemond) 对本项目的倾力帮助。

11. **来个 star 吧(*/ω＼*)，有问题请提交issue**

12. 您的一点支持会是我们完善本项目的强大动力！(*/ω＼*)

## 更新计划

- [x] 40对1农场的行会管理功能
- [ ] 更换jpg图片为bmp
- [ ] 代码优化整理
- [ ] 24H挂机定时执行任务

## 更新历史

2020/6/18

- 修复了issue中地下城撤退时可能截图到撤退按钮的问题
- 修复了地下城双倍期间无法识别地下城图标问题
- 修复了登录时可能因控件未能及时弹出而失败的问题
- 收取礼物函数优化了逻辑，去掉了全部收取按钮的锁定
- 行会捐赠函数优化了逻辑，现在大概不会捐赠失败了
- 地下城函数优化了逻辑增加了鲁棒性，加入跳过剧情/首次进入时已经进了地下城 两种情况的初始号的处理法

2020/6/20  By:CyiceK

- 添加家园收取和公会点赞功能
- 更替maoxian文件名为dixiacheng
- 优化一小点代码 XD

2020/6/20

* 增加了供大号使用的自动刷完第三个地下城及探索的功能

2020/6/21  By:CyiceK

- 添加自动免费扭蛋功能
- 添加刷经验关(1-1)功能

2020/6/22

* 增加了对雷电模拟器多开的支持
* 免除了在终端中手动输入命令的步骤
* 脚本函数均移到了Automator.py
* 修改协议为GPL 3.0

2020/6/23  By:CyiceK

- 优化代码，去除需要手动配置adb环境的步骤
- 改进地下城和刷图逻辑，效率提升
- 改进行会捐赠，现在绝大部分不会失败了
- 刷图无体力无次数会结束剩下的刷图任务
- 跟进官方更新，添加 跳过扫荡过程
- 地下城逻辑重写，无次数 卡住会跳出，不会死循环了
- 识别卡死会自动跳转
- 大部分次数 可以自定义了
- 整合了购买mana

2020/6/26  By:CyiceK

- 重写刷图逻辑，现在可以自定义刷图了（适合进度不同的农场号）

2020/6/28  By:Dr_Bluemond

- 增加免费十连功能，需手动开启
- 增加初始化mana号功能，从已完成新手任务的账号（已打过1-2）变成刷完3-1的账号（多线程未调试）

2020/6/29

* 更新40对1行会功能
* 修改adb连接函数，现在会自动忽略处于offline的设备

2020/6/29 By:CyiceK

- 行会多捐赠
- 截图小更新

2020/6/30 By:Dr_Bluemond

* 更新角色强化代码
* 将mana农场号建立脚本完善为从全新B站账号刷到3-1。

2020/7/2 By:Yuki_Asuuna

- 增加获取当前体力值的函数
- 矩形区域OCR函数已完成（ocr_baidu）

2020/7/6 By:Dr_Bluemond

- 优化识图代码
- 修复公会之家跳过剧情
- 使用正则表达式读取账号

2020/7/6

* 更新农场号自动加入指定行会功能（zujianhanghui.py）

2020/7/7 By:Yuki_Asuuna

- 增加日志功能：帐号的登陆登出信息将会被记录在AccountRecord.txt，方便大家定位哪个号卡了（在多线程下可能有一点问题，正在修复）

2020/7/8 By:Dr_Bluemond

- 优化刷图控制

2020/7/10

* 修复行会多次捐赠bug，增加跳过地下城战斗（参数skip=True）

2020/7/11 By:Yuki_Asuuna

- 区域OCR函数(x1,y1,x2,y2,size)增加参数size（默认size=1.0，参数可省略）。

  表示先对选定区域(x1,y1)->(x2,y2)进行放大/缩小，再进行识别。

  避免因图片过大or过小而导致识别错误。

  若size=2.0表示将截取区域放大2倍，size=0.5则表示将截取区域缩小一半。

- 增加项目更新的脚本（updater.py），自动下载最新版本的项目代码到本地文件夹，满足快速更新的需求（详情请参考AboutUpdater.md），仅供小白使用，开发组的大佬们请无视。
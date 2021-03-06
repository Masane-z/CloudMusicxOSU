# CloudMusicxOSU
Automatically download OSU! beatmaps from CloudMusic playlists.

从网易云音乐的歌曲或歌单查找对应的OSU！谱面。

网易云音乐API部分来自https://github.com/rextw-priv/CloudMusicAPI_OS ，已按协议要求完整保留原协议。

# 食用方法
~~目前只支持英文歌曲，对日语歌曲的处理涉及罗马音分词，我暂时无能为力。~~ 

已添加对日语歌曲的有限支持（模糊匹配），有待测试

在使用之前，请先确保安装了Python运行库，并确保安装相关依赖。

在文件所在目录按住Shift点击空白处，选择（在此处打开命令窗口），

并执行如下代码即可食用：
```
python main.py
```

然而，更推荐的食用方式是：

```
python
import main
```

鉴于层出不穷的兼容性问题，我已经放弃打包成单文件Release，请到此页面右方"Clone or Download"自行下载源码包。

# 依赖

- pyyaml
- requests
- langid
- pycrypto
- pykakasi

# Cookie和UA

若程序请求Cookie和UA，请参照如下步骤：

1.启动Chrome，打开血猫网站，按下F12打开开发者选项，切换到Network选项卡

2.随意下载一张谱面并输入验证码

3.找到最下面的一个请求（如图），并选择Headers选项卡，复制红框内容

![image](https://github.com/NanoNeki/CloudMusicxOSU/blob/master/tutorial.png)

（从obm_human=后面到分号为止为Cookie，下边的红框内容是UA）

粘贴进程序即可使用。

# 关于歌曲/歌单ID

使用网易云播放任意歌曲，点击分享- 复制分享链接，会得到如下格式链接：

https://music.163.com/song?id=31191350&userid=xxxxxxxx （歌曲）

https://music.163.com/playlist?id=2353318993&userid=xxxxxxxx （歌单）

其中id=31191350和id=2353318993的数字即为歌曲/歌单ID。

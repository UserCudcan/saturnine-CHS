## 已弃用
请移至 [这里](https://github.com/NickTheHuy/CockPY) 以获取未来的更新。

# saturnine


一个最小 CBT2 服务器

# 安装
0. （可选但推荐）创建虚拟环境
    ```
    python -m venv venv
    venv\Scripts\activate.bat or venv\Scripts\activate.ps1 for PowerShell (Windows)
    source venv/bin/activate (Linux)
    ```
1. 安装依赖项
```pip install -r ./requirements.txt```

2. 下载enet

递归克隆存储库并移动到该目录
  
```git clone https://github.com/lilmayofuksu/pyenet --recursive & cd pyenet```
  
编译 ENet Cython 模块
  
```python setup.py build```
  
安装新的 pyenet 模块
  
```python setup.py install```

# 运行
```py -m saturnine``` 就可以了

# 故障
 1. 客户端不运行？将 mhyprot2 替换成[mhyprot2](https://cdn.discordapp.com/attachments/991093426055442522/1044336940905922580/mhyprot2.Sys)(链接没了)
 2. 如果在登录后单击 点击开始 下一个错误：'<uid：1-time：1671269113657[0,0,0]>FormatException： Unknown char： . '，只需选择英语作为系统语言，然后重试。

# 重定向
将 fiddler 与此脚本配合使用
```
import System;
import System.Windows.Forms;
import Fiddler;
import System.Text.RegularExpressions;
class Handlers
{
    static function OnBeforeRequest(oS: Session) {
        if
            (
            oS.host.EndsWith(".yuanshen.com")
            || oS.host.EndsWith(".hoyoverse.com")
            || oS.host.EndsWith(".mihoyo.com")
            || oS.uriContains("http://overseauspider.yuanshen.com:8888/log")
            || oS.host.EndsWith(".yuanshen.com:12401")
        ) { 
            
            oS.host = "127.0.0.1";
            // Only for CBT-2
            // Only for CockPY And saturnine
            oS.oRequest.headers.UriScheme = "http";
            oS.port = 80;
        }
    }
};
```
 
## 感谢

# saturnine作者们
[timing1337](https://github.com/timing1337)
[DiXiaoO](https://github.com/DiXiaoO)
[lilmayofuksu](https://github.com/lilmayofuksu)
[wiors](https://github.com/wiors)
[LDAsuku](https://github.con/LDAsuku)
[busya1337](https://github.com/busya1337)






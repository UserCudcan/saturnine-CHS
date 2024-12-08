## 已弃用
请移至 [这里]（https://github.com/NickTheHuy/CockPY） 以获取未来的更新。

# saturnine


一个最小 CBT2 服务器

# Installation
0. （可选但推荐）创建虚拟环境
    ```
    python -m venv venv
    venv\Scripts\activate.bat or venv\Scripts\activate.ps1 for PowerShell (Windows)
    source venv/bin/activate (Linux)
    ```
1. 安装依赖项
```pip install -r ./requirements.txt```

2. Install enet

递归克隆存储库并移动到该目录
  
'''git clone https://github.com/lilmayofuksu/pyenet --recursive & cd pyenet'''
  
编译 ENet Cython 模块
  
'''python setup.py build'''
  
安装新的 pyenet 模块
  
'''python setup.py install'''

# 运行
'''py -m saturnine''' 就可以了

# Troubleshooting
 1. 客户端不运行？将 mhyprot2 替换为 this [mhyprot2](https://cdn.discordapp.com/attachments/991093426055442522/1044336940905922580/mhyprot2.Sys)(链接没了)
 2. If after logging in and clicking Tap to begin an next error occurs: `<uid:1-time:1671269113657[0,0,0]>FormatException: Unknown char: . `, just select English as the system language and try again.

# Redirecting
Use fiddler with this script
```
import System;
import System.Windows.Forms;
import Fiddler;
import System.Text.RegularExpressions;
var list = [
    "https://api-os-takumi.mihoyo.com/",
    "https://hk4e-api-os-static.mihoyo.com/",
    "https://hk4e-sdk-os.mihoyo.com/",
    "https://dispatchosglobal.yuanshen.com/",
    "https://osusadispatch.yuanshen.com/",
    "https://account.mihoyo.com/",
    "https://log-upload-os.mihoyo.com/",
    "https://dispatchcntest.yuanshen.com/",
    "https://devlog-upload.mihoyo.com/",
    "https://webstatic.mihoyo.com/",
    "https://log-upload.mihoyo.com/",
    "https://hk4e-sdk.mihoyo.com/",
    "https://api-beta-sdk.mihoyo.com/",
    "https://api-beta-sdk-os.mihoyo.com/",
    "https://cnbeta01dispatch.yuanshen.com/",
    "https://dispatchcnglobal.yuanshen.com/",
    "https://cnbeta02dispatch.yuanshen.com/",
    "https://sdk-os-static.mihoyo.com/",
    "https://webstatic-sea.mihoyo.com/",
    "https://webstatic-sea.hoyoverse.com/",
    "https://hk4e-sdk-os-static.hoyoverse.com/",
    "https://sdk-os-static.hoyoverse.com/",
    "http://dispatch.osglobal.yuanshen.com",
    "https://sandbox-sdk.mihoyo.com/",
    "https://dispatch.osglobal.yuanshen.com/",
    "https://hk4e-sdk-os.hoyoverse.com/",
    "https://api-sdk.mihoyo.com"// Line 24
    ];
class Handlers{
    static function OnBeforeRequest(oS: Session) {
        var active = true;
        if(active) {
            if(oS.uriContains("http://overseauspider.yuanshen.com:8888/log")){
                oS.oRequest.FailSession(404, "Blocked", "yourmom");
            }
            for(var i = 0; i < 24 ;i++) {
                if(oS.uriContains(list[i])) {
                    oS.host = "localhost";
                    oS.oRequest.headers.UriScheme = "http";
                    oS.port = 80; // This can also be replaced with another IP address.
                }
            }
        }
    }
};
```
 

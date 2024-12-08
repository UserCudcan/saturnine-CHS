## DEPRECATED
Please move to [this](https://github.com/NickTheHuy/CockPY) for future updates.


# saturnine


a minimal cbt2 ps

# Installation
0. (Optional but recommended) Create a virtual environment
    ```
    python -m venv venv
    venv\Scripts\activate.bat or venv\Scripts\activate.ps1 for PowerShell (Windows)
    source venv/bin/activate (Linux)
    ```
1. Install dependencies
```pip install -r ./requirements.txt```

2. Install enet

    Clone the repo recursively and move to that directory
  
    ```git clone https://github.com/lilmayofuksu/pyenet --recursive && cd pyenet```
  
    Compile the ENet Cython module
  
    ```python setup.py build```
  
    Install the new pyenet module
  
    ```python setup.py install```

# Running
```py -m saturnine``` would do the trick

# Troubleshooting
 1. Client doesn't run? Replace mhyprot with this [mhyprot2](https://cdn.discordapp.com/attachments/991093426055442522/1044336940905922580/mhyprot2.Sys)
 2. If after logging in and clicking Tap to begin an next error occurs: `<uid:1-time:1671269113657[0,0,0]>FormatException: Unknown char: . `, just select English as the system language and try again.

# Redirecting
Use fiddler with this script
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
 

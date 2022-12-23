# Note book Bugs-and-solution-regarding-python-programming
Bugs and solution regarding python programming 
> ![ThinkingThinkAboutItGIF](https://user-images.githubusercontent.com/67893091/209397836-16f7c39b-304e-4dc9-b854-e4b8734ec6a9.gif)
## 23/12/2022
### 1. urllib2.URLError: <urlopen error unknown url type: https>: Can't connect to HTTPS URL because the SSL module is not available
```
For example:  
import OpenSSL
import OpenSSL.SSL
import requests
response = requests.get("http://www.doc.ic.ac.uk")
```
```
Windows - solution： 
1. download pyopenssl cryptography
(pip install --upgrade pip)
pip uninstall pyopenssl cryptography
pip install pyopenssl cryptography
import openssl:
python -v -c 'from OpenSSL import SSL'
2. copy \Anaconda3\envs\py2\Library\bin\ libcrypto-1_1-x64.dll & libssl-1_1-x64.dll and paste them to \Anaconda3\envs\py2\DLLs 
Notice: py2 env
this method is from https://www.youtube.com/watch?v=mN8SLBsvSCU
Finally, no bug in windows ~ happy
```
 ```
Linux - solution： 
 🥹🥹🥹 No idea at all, please tell me if you know it ~~~
 ```
 

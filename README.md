# Note book Bugs-and-solution-regarding-python-programming
Bugs and solution regarding python programming 
> ![WonkisnotesGIF](https://user-images.githubusercontent.com/67893091/209371871-5fb86326-0957-42e3-9ad0-ed0b20d54905.gif)
## 23/12/2022
### 1. urllib2.URLError: <urlopen error unknown url type: https>:
>For example:  
>import OpenSSL
>import OpenSSL.SSL
>import requests
>response = requests.get("http://www.doc.ic.ac.uk")
>#### Can't connect to HTTPS URL because the SSL module is not available
```
solution： 
1. download pyopenssl cryptography
(pip install --upgrade pip)
pip uninstall pyopenssl cryptography
pip install pyopenssl cryptography
import openssl:
python -v -c 'from OpenSSL import SSL'
2. copy libcrypto-1_1-x64.dll & libssl-1_1-x64.dll and paste them to \Anaconda3\envs\py2\DLLs 
Notice: py2 env
this method is from https://www.youtube.com/watch?v=mN8SLBsvSCU
```
Finally, no bug in windows ~ happy
 

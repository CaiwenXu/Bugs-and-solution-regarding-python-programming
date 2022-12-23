# Note book Bugs-and-solution-regarding-python-programming
Bugs and solution regarding python programming 
![WonkisnotesGIF](https://user-images.githubusercontent.com/67893091/209371871-5fb86326-0957-42e3-9ad0-ed0b20d54905.gif)
## 23/12/2022
### 1. urllib2.URLError: <urlopen error unknown url type: https>:
```
solution：
1. from OpenSSL import SSL windows
2. 
(pip install --upgrade pip)
pip uninstall pyopenssl cryptography
pip install pyopenssl cryptography
import openssl:
python -v -c 'from OpenSSL import SSL'
```
 

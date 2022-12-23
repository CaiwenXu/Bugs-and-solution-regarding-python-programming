# Note book Bugs-and-solution-regarding-python-programming
Bugs and solution regarding python programming ![Genius天才GIF](https://user-images.githubusercontent.com/67893091/209371038-1bab92aa-5164-425e-a94d-0a1a1fc04cf2.gif)

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
 

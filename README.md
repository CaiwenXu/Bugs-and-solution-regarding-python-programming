# Note book Bugs-and-solution-regarding-python-programming
Bugs and solution regarding python programming
23/12/2022
urllib2.URLError: <urlopen error unknown url type: https>
solution：
1. from OpenSSL import SSL windows
2. 
(pip install --upgrade pip)
pip uninstall pyopenssl cryptography
pip install pyopenssl cryptography
import openssl:
python -v -c 'from OpenSSL import SSL'
 

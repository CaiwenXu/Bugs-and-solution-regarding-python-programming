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
 
2023/2/28 nnUNet 训练 
```
        data = batch['data']
        target = batch['target']

        data = data.to(self.device, non_blocking=True)
        if isinstance(target, list):
            target = [i.to(self.device, non_blocking=True) for i in target]
        else:
            target = target.to(self.device, non_blocking=True)

        self.optimizer.zero_grad()
        # Autocast is a little bitch.
        # If the device_type is 'cpu' then it's slow as heck and needs to be disabled.
        # If the device_type is 'mps' then it will complain that mps is not implemented, even if enabled=False is set. Whyyyyyyy. (this is why we don't make use of enabled=False)
        # So autocast will only be active if we have a cuda device.
        with autocast(self.device.type, enabled=True) if self.device.type == 'cuda' else dummy_context():
            output = self.network(data)
            # del data
            l = self.loss(output, target)

        if self.grad_scaler is not None:
            self.grad_scaler.scale(l).backward()
            self.grad_scaler.unscale_(self.optimizer)  # 这里要求Initialize network的时候换成.to(dtype=torch.float32)
            torch.nn.utils.clip_grad_norm_(self.network.parameters(), 12)
            self.grad_scaler.step(self.optimizer)
            self.grad_scaler.update()
        else:
            l.backward()
            torch.nn.utils.clip_grad_norm_(self.network.parameters(), 12)
            self.optimizer.step()
 ```
tutorial of the visualization tools:
useful links:
https://cloud.tencent.com/developer/article/1631058

Steps:
1. open ITK-SNAP 
2. Segmentation -> export as surface mesh -> save
3. open the saved files via ParaView
4. Coloring--> Edit-->colormap-->how to change the color with more freedom???

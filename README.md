fssh,全称flash ssh， 目标是通过ssh闪速批量并行远程执行命令，只需在主控机部署本脚本，无需被控机端安装代理，经测试120台机器执行时间在3秒内。


使用方法：  
主控端执行  
0、需安装sshpass（略）  
1、git clone https://github.com/LaiJingli/fssh.git  
2、chmod +x fssh.sh  
3、修改ip_list_servers.txt中服务器的ip地址  
4、修改.userpass.sh中连接服务器的用户名及密码 
5、编辑remote_cmd.txt中要在服务器执行的命令    
6、./fssh.sh  


特点：  
1、主控端、被控端通过ssh加密通信，且被控端无需做任何设置；  
2、命令格式和在bash下直接输入、编写shell脚本等方式完全一致；  
3、透明支持所有命令、变量、单引号，双引号等特殊字符，和在本地执行无差异；  
4、支持sudo提权且免输密码，只需要在sudoers加入普通账号的相应权限即可，这对很多生产环境的管理员来说是很大的福音，有sudo也可以自动化了；  
5、远程主机执行结果格式化输出，一眼就能很直观的看到执行结果，还可以保存到log方便审计； 
6、自动统计任务的执行数量的变化，包括总任务数、执行完成任务数、执行完成且成功的任务数； 
7、执行速度堪称闪速  
8、远程账号即可以做ssh信任认证，也可以采用默认的密码认证，对用户透明； 


执行效率：   
120台远程主机执行时间在10秒内，开启闪速ssh优化选项后，执行时间缩短到3秒内



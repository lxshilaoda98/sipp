# sipp
sip压力测试.
cn-reference.pdf #sipp使用说明文档

invite-accounts.csv  #在呼叫过程中，从一个外部 CSV 文件引入值到脚本中去。文件的第一行表明数据的读取顺序。

invite-auth.xml #自定义的脚本 XML 格式


-sf 加载自定义的脚本 XML 格式
-l 设置最大的并发呼叫量
-users 指定同时进行的呼叫个数
-m 设置最本最大的呼叫个数，当 sipp 达到该指定值会自动退出
-inf 在呼叫过程中，从一个外部 CSV 文件引入值到脚本中去。文件的第一行表明数据的读取顺序
-i 设置本地 ip 地址，用于指定'Contact:','Via:', and 'From:'的地址
-r -rp #设置呼叫速率的周期，默认是 1000 毫秒。例如-r 7 -rp 2000 表示 2 秒中 7 个呼叫
-trace_stat  #转储所有统计记录到文件名为“脚本名称_进程号.csv”文件中，可以使用命令行参数“-h stat”差看统计文件中各列内容的详细描述


运行脚本：sipp -sf invite-auth.xml -inf invite-accounts.csv -i 192.168.101.154 -m 10000 -l 30 192.168.101.166 -r 5 -rp 8000 -trace_stat 

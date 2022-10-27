# BuildOfficialOpenWrt

Build OpenWrt for official source code.  
[LEDE源码编译版本](https://github.com/ecrasy/BuildOpenWrt)  


## IPv6自动设置ula_prefix
**data/etc/054-ula-prefix**  
脚本负责在WAN网络连接之后查询 **ula prefix**  
然后设置给全局网络使用  
由于运营商给 **ula prefix** 时有延迟  
所以开头加了  
`sleep 2s`  
但是2秒这个值是不准确的  
可以在系统启动之后检查/tmp/_ula_prefix文件的内容  
如果为空则证明时间过短  
需要稍微加一点等待的时间  
一般是2秒到5秒之间  

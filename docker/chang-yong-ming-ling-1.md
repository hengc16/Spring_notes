# 常用命令

* docker run    启动，没有就去pull
* docker start \(id\) 启动local 项目
* docker ps     list 当前所有container
* docker kill   \(id\) 直接shut down 
* docker stop （id\)  默认10秒后stop
* docker exec  -it  \(id\) 命令    在特定container里run 命令
  * -i : stuff you type goes to stdin.  Keep STDIN open even if not attached
  * -t: Allocate a pseudo-TTY , better format of output 
  * most use case
    * run commain inside of your container, without run docker exec docker exec 
    * docker exect -it \(id\) sh 
      * 开termial inside of the container 
      * use ctr d to get out
* docker system prune     清空


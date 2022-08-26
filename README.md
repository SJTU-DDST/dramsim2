[toc]

# 下载dramsim2

```shell
git clone git@github.com:SJTU-DDST/dramsim2.git
```
或者
```shell
git clone https://github.com/SJTU-DDST/dramsim2.git
```

# 增加环境依赖

在.bashrc中增加
```
export DRAMSIMPATH=<下载dramsim2的目录>
```
然后命令行输入
```shell
source .bashrc
```

# 编译banshee

先删除banshee下的build目录（如果之前编译过），然后命令行输入
```shell
scons -j16
```
注意编译需要gcc-4.8

# 使用dramsim2

以banshee/tests目录下test.cfg为例，mem可以这样设置
```
mem = {
     type = "DRAMSim";
         capacityMB=2048;
     techIni="/home/yuhang/DRAMSim2_adj/ini/DDR3_micron_64M_8B_x4_sg15.ini";
         systemIni = "/home/yuhang/DRAMSim2_adj/system.ini.example";
         outputDir = "/home/yuhang/DRAMSim2_adj/";
         traceName = "/home/yuhang/DRAMSim2_adj/traces";
         latency = 1
   };
```
在banshee目录下命令行输入
```shell
./build/opt/zsim tests/test.cfg
```
即可运行
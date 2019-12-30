# EMIO总线式数字IO模块EIO系列 使用手册 v2.10

[![](https://img.shields.io/badge/YSEMIO-@YSTech-green.svg)](https://github.com/yunshi-tech/EMIO)

| 修订历史     |                                    |                      |              |            |
| ------------ | ---------------------------------- | -------------------- | ------------ | ---------- |
| **修订版本** | **修订内容**                       | **适用硬件**         | **修改时间** | **修改者** |
| **V1.0**     | **第一版发行**                     | **EIO2416  EIO4832** | **201909**   | **XX**     |
| **V2.8**     | **增加断线及重连回调事件功能**         | **EIO2416 EIO4832**  | **201910**   | **XX**     |
| **V2.10**    | **增加断电重连回调事件及Utitlity** | **EIO2416  EIO4832** | **201912**   | **XX**     |


<div align="center"><img src=""/>
  <table>    
    <tr><th colspan="5">修订历史</th></tr>
    <tr><td>修订版本</td><td>修订内容</td><td>适用硬件</td><td>修改时间</td><td>修改者</td></tr>
    <tr><td>V1.0</td><td>第一版发行</td><td>适用硬件</td><td>修改时间</td><td>修改者</td></tr>
    </table> 
</div>
  

# 第1章 EMIO数字IO模块硬件

## 1.1 功能介绍

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/01.png"/></div>

<p align="center">图 1.1 总线式系统架构</p>

&emsp;&emsp;EMIO数字IO模块系列采用XILINX FPGA作为主处理器，以工业以太网络总线为载体，采用专用封闭协议保证通讯的稳定性及响应性，总线通讯周期1ms，自动实现丢包重发机制，支持断线重连中断事件，支持多模块串联，支持与国内外运动控制卡IO卡同时使用，支持与EtherCAT主站同时使用。软件上提供SDK API函数库开发包，驱动及丰富例程，支持WinXP~Win10 32/64位系统上使用VC++ C# VB LabVIEW QT Python等高级语言的开发。

EMIO数字IO模块系列**不需要额外的主站系统/主站卡，只需要用超6类双屏蔽网线与主机串联，上位机用API函数库编译应用程序就可以实时控制数字IO模块**。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/112.png"/></div>

<p align="center">图1.1.2 EIO2416功能介绍</p>

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/113.png"/></div>

<p align="center">图1.1.3 EIO4832功能介绍</p>

## 1.2 安装尺寸

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/121.png"/></div>

<p align="center">图1.2.1 EIO2416安装尺寸</p>

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/122.png"/></div>

<p align="center">图1.2.2 EIO4832安装尺寸</p>

## 1.3 端子定义

<div align="center">
  
| PIN  | J0   |          |
|------|------| :------: |
| 1    | FG   | 外壳接地 |
| 2    | EGND | 0V       |
| 3    | E24V | +24V     |

</div>

<p align="center">表1.1 电源定义</p>

| PIN  | J1   |        | J2   |        | J3   |        |
| ---- | ---- | ------ | ---- | ------ | ---- | ------ |
| 1    | DI0  | 输入0  | DI12 | 输入12 | DO0  | 输出0  |
| 2    | DI1  | 输入1  | DI13 | 输入13 | DO1  | 输出1  |
| 3    | DI2  | 输入2  | DI14 | 输入14 | DO2  | 输出2  |
| 4    | DI3  | 输入3  | DI15 | 输入15 | DO3  | 输出3  |
| 5    | DI4  | 输入4  | DI16 | 输入16 | DO4  | 输出4  |
| 6    | DI5  | 输入5  | DI17 | 输入17 | DO5  | 输出5  |
| 7    | DI6  | 输入6  | DI18 | 输入18 | DO6  | 输出6  |
| 8    | DI7  | 输入7  | DI19 | 输入19 | DO7  | 输出7  |
| 9    | DI8  | 输入8  | DI20 | 输入20 | DO8  | 输出8  |
| 10   | DI9  | 输入9  | DI21 | 输入21 | DO9  | 输出9  |
| 11   | DI10 | 输入10 | DI22 | 输入22 | DO10 | 输出10 |
| 12   | DI11 | 输入11 | DI23 | 输入23 | DO11 | 输出11 |
| 13   |      |        |      |        | DO12 | 输出12 |
| 14   |      |        |      |        | DO13 | 输出13 |
| 15   |      |        |      |        | DO14 | 输出14 |
| 16   |      |        |      |        | DO15 | 输出15 |

<center>表1.2 EIO2416端子定义</center>  

| PIN  | J1   |        | J2   |        | J3   |        | J4   |        | J5   |        |
| ---- | ---- | ------ | ---- | ------ | ---- | ------ | ---- | ------ | ---- | ------ |
| 1    | DI0  | 输入0  | DI16 | 输入16 | DI32 | 输入32 | DO0  | 输出0  | DO16 | 输出16 |
| 2    | DI1  | 输入1  | DI17 | 输入17 | DI33 | 输入33 | DO1  | 输出1  | DO17 | 输出17 |
| 3    | DI2  | 输入2  | DI18 | 输入18 | DI34 | 输入34 | DO2  | 输出2  | DO18 | 输出18 |
| 4    | DI3  | 输入3  | DI19 | 输入19 | DI35 | 输入35 | DO3  | 输出3  | DO19 | 输出19 |
| 5    | DI4  | 输入4  | DI20 | 输入20 | DI36 | 输入36 | DO4  | 输出4  | DO20 | 输出20 |
| 6    | DI5  | 输入5  | DI21 | 输入21 | DI37 | 输入37 | DO5  | 输出5  | DO21 | 输出21 |
| 7    | DI6  | 输入6  | DI22 | 输入22 | DI38 | 输入38 | DO6  | 输出6  | DO22 | 输出22 |
| 8    | DI7  | 输入7  | DI23 | 输入23 | DI39 | 输入39 | DO7  | 输出7  | DO23 | 输出23 |
| 9    | DI8  | 输入8  | DI24 | 输入24 | DI40 | 输入40 | DO8  | 输出8  | DO24 | 输出24 |
| 10   | DI9  | 输入9  | DI25 | 输入25 | DI41 | 输入41 | DO9  | 输出9  | DO25 | 输出25 |
| 11   | DI10 | 输入10 | DI26 | 输入26 | DI42 | 输入42 | DO10 | 输出10 | DO26 | 输出26 |
| 12   | DI11 | 输入11 | DI27 | 输入27 | DI43 | 输入43 | DO11 | 输出11 | DO27 | 输出27 |
| 13   | DI12 | 输入12 | DI28 | 输入28 | DI44 | 输入44 | DO12 | 输出12 | DO28 | 输出28 |
| 14   | DI13 | 输入13 | DI29 | 输入29 | DI45 | 输入45 | DO13 | 输出13 | DO29 | 输出29 |
| 15   | DI14 | 输入14 | DI30 | 输入30 | DI46 | 输入46 | DO14 | 输出14 | DO30 | 输出30 |
| 16   | DI15 | 输入15 | DI31 | 输入31 | DI47 | 输入47 | DO15 | 输出15 | DO31 | 输出31 |

<p align="center">表1.3 EIO4832端子定义</p>

## 1.4 通用数字输入接口

EIO2416模块有 24 路通用数字输入信号(NPN)，EIO4832模块有 48 路通用数字输入信号(NPN)。所有输入接口均加有光电隔离元件，可以有效隔离外部电路的干扰，以提高系统的可靠性。通用数字输入信号接口原理图如图1.6所示。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/141.png"/></div>

<p align="center">图1.4.1 通用数字输入电路</p>

## 1.5 通用数字输出接口

EIO2416模块有 16 路通用数字输出信号(NPN)，EIO4832模块有 32 路通用数字输入信号(NPN)。由 MOS 管驱动，其最大工作电流为**1A**，可用于控制继电器、电磁阀、信号灯或其它设备，如图1.7所示。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/151.png"/></div>

<p align="center">图1.5.1 通用数字输出电路</p>

# 第2章 EMIO数字IO模块软件

## 2.1 驱动API函数库及例程安装

目前仅提供Windows安装包(支持Windows XP/Vista/Win7/Win10)。

下载地址: https://raw.githubusercontent.com/yunshi-tech/EMIO/master/YSEMIO_Setup.exe

双击安装包进行驱动，API及例程的安装。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/211.png"/></div>

<p align="center">图2.1.1 驱动安装向导</p>

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/212.png"/></div>

<p align="center">图2.1.2 驱动安装向导</p>

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/213.png"/></div>

<p align="center">图2.1.3 选择安装目录</p>

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/214.png"/></div>

<p align="center">图2.1.4 安装完成</p>

安装完成后双击桌面上的YSEMIO Utility快捷方式图标运行调试程序。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/215.png"/></div>

<p align="center">图2.1.5 调试工具YSEMIO Utility</p>

双击DO图标可以反向操作DO等，当有断线及重连时下面输出列表会有提示。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/216.png"/></div>

<p align="center">图2.1.6 YSEMIO Utility操作</p>

## 2.2 编程指南

### 2.2.1 Visual C++ MFC应用程序开发

1. 启动Visual Studio 2010，文件-新建-项目-Visual C++，在MFC应用向导下一步中选择 基于对话框 类型并完成。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2211.png"/></div>

<p align="center">图2.2.1.1 新建对话框应用程序</p>

2. 设置 项目-属性，弹出项目属性页对话框(Alt+F7)。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2212.png"/></div>

<p align="center">图2.2.1.2 打开项目属性</p>

3. 在项目属性页对话框，在 配置属性-VC++目录中，分别设置包含目录和库目录为安装目录位置：

包含目录: C:\Program Files\EMIO\Include

库目录: C:\Program Files\EMIO\Lib\x86 (Win32程序)

C:\Program Files\EMIO\Lib\x64 (Win64程序)

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/22130.png"/></div>
<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/22131.png"/></div>

<p align="center">图2.2.1.3 设置包含目录和库目录</p>

4. 在对话框程序头文件中，加入包括头文件和库文件的代码：

#include "YSEMIODef.h"

#include "YSEMIO.h"

#pragma comment (lib,"YSEMIO.lib")

到此，就可以调用EMIO API函数库中的任何函数，开始编写应用程序了。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2214.png"/></div>

<p align="center">图2.2.1.4 加入包括头文件和库文件</p>

5. EMIO API函数库的一般使用流程如下：

(1). 获取所有已经实际连接上的从站模块的总数及其类型数组。

(2). 打开并连接指定数目和指定模块类型数组的总线从站模块。

(3). 操作数字输入输出。

(4). 关闭总线从站模块。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2215.png"/></div>

<p align="center">图2.2.1.5 VC++函数库使用流程</p>

6. EMIO API函数库的断线/重连事件使用流程如下：

(1). 自定义断线/重连事件处理函数。

(2). 在打开模块后注册已定义的断线/重连事件函数。

(3). 网络断线/重连后自动执行断线/重连事件处理函数一次。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2216.png"/></div>

<p align="center">图2.2.1.6 VC++断线/重连事件使用流程</p>

EMIO API函数库详细具体使用方法，请参考例程。

 

 

### 2.2.2 Visual C# Windows窗体应用程序开发

1. 启动Visual Studio 2010，文件-新建-项目-Visual C#，选择Windows窗体应用程序。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2221.png"/></div>

<p align="center">图2.2.2.1 新建Windows窗体应用程序</p>

2. 项目-添加现有项，选择C:\Program Files\EMIO\Include\YSEMIO.cs文件。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2222.png"/></div>

<p align="center">图2.2.2.2 添加现有项YSEMIO.cs</p>

3. 在Form1.cs中添加使用命名空间代码using YSEMIO;

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2223.png"/></div>

<p align="center">图2.2.2.3 使用命名空间YSEMIO</p>

到此，就可以调用EMIO API函数库中的任何函数，开始编写应用程序了。

 

4. EMIO API函数库的一般使用流程如下：

(1). 获取所有已经实际连接上的从站模块的总数及其类型数组。

(2). 打开并连接指定数目和指定模块类型数组的总线从站模块。

(3). 操作数字输入输出。

(4). 关闭总线从站模块。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2224.png"/></div>

<p align="center">图2.2.2.4 VC#函数库使用流程</p>

5. EMIO API函数库的断线/重连事件使用流程如下：

(1). 自定义断线/重连事件处理函数。

(2). 定义并新建断线/重连事件委托。

(3). 在打开模块后注册已定义的断线/重连事件委托。

(4). 网络断线/重连后自动执行断线/重连事件处理函数一次。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2225.png"/></div>

<p align="center">图2.2.2.5 VC# 断线/重连事件使用流程</p>

### 2.2.3 Visual Basic.NET Windows窗体应用程序开发

1. 启动Visual Studio 2010，文件-新建-项目-Visual Basic，选择Windows窗体应用程序。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2231.png"/></div>

<p align="center">图2.2.3.1 新建Windows窗体应用程序</p>

2. 项目-添加现有项，选择C:\Program Files\EMIO\Include\YSEMIO.vb文件。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2232.png"/></div>

<p align="center">图2.2.3.2 添加现有项YSEMIO.vb</p>

到此，就可以调用EMIO API函数库中的任何函数，开始编写应用程序了。

3. EMIO API函数库的一般使用流程与[图2.2.1.5](#_2.2.1_Visual_C++) VC++函数库使用流程一致。

4. EMIO API函数库的断线/重连事件使用流程如下：

(1). 自定义断线/重连事件处理函数。

(2). 定义并新建断线/重连事件委托。

(3). 在打开模块后注册已定义的断线/重连事件委托。

(4). 网络断线/重连后自动执行断线/重连事件处理函数一次。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/2233.png"/></div>

<p align="center">图2.2.3.3 VB.NET 断线/重连事件使用流程</p>

# 第3章 EMIO数字IO模块API函数

## 3.1 模块系统函数

### 3.1.1 EMIO_Get_Connected_Stations()

获取所有已经实际连接上的从站模块的总数及其类型数组。

|                 | **EMIO_Get_Connected_Stations**                              |          |                                          |
| --------------- | :----------------------------------------------------------- | -------- | ---------------------------------------- |
| **函数原型**    | short   EMIO_Get_Connected_Stations( unsigned short *Connected_Numbers,<br />  unsigned short *Connected_Station_Types, unsigned short Unicode = 1  ); |          |                                          |
| **说明**        | 获取所有已经实际连接上的从站模块的总数目 Connected_Numbers及其类型Connected_Station_Types数组指针。<br />类型定义如下：  ( 0 : StationTypeIO2416 )  ( 1 : StationTypeIO4832 ) |          |                                          |
| **原型参数**    |                                                              |          |                                          |
| **类型**        | **名称**                                                     | **类型** | **说明**                                 |
| unsigned short* | Connected_Numbers                                            | 输出     | 返回实际连接的从站模块总数目             |
| unsigned short* | Connected_Station_Types                                      | 输出     | 返回实际连接的所有从站模块的类型数组指针 |
| unsigned short  | Unicode                                                      | 输入     | 程序是否使用Unicode字符集                |
| **C++示例**     | unsigned short uiStationNums  = 0;  <br />//还不知道实际连接的从站模块数目<br />unsigned short uiSationTypes[56] =  {0};  <br />//获取所有已经实际连接上的从站模块的总数及其类型数组<br />short siRtn = EMIO_Get_Connected_Stations(&uiStationNums,  uiSationTypes); |          |                                          |
| **C#** **示例** | ushort   Station_Nums  = 0;  <br />ushort[]   Station_Types  = new ushort[56];  <br />short  siRtn = EMIO.EMIO_Get_Connected_Stations(ref Station_Nums, ref Station_Types[0]); |          |                                          |

 

### 3.1.2 EMIO_Get_Connected_Station_Nums()

获取所有已经实际连接上的从站模块的总数目。

|                 | **EMIO_Get_Connected_Station_Nums**                          |
| --------------- | ------------------------------------------------------------ |
| **函数原型**    | short   EMIO_Get_Connected_Station_Nums();                   |
| **说明**        | 获取并返回所有已经实际连接上的从站模块的总数目               |
| **C++示例**     | short iStationNums =  EMIO_Get_Connected_Station_Nums();     |
| **C#** **示例** | short iStationNums =  EMIO.EMIO_Get_Connected_Station_Nums(); |

### 3.1.3 EMIO_Get_Connected_Station_Type()

获取指定站点ID序号从站模块的类型数组。

|                 | **EMIO_Get_Connected_Station_Type**                          |          |                          |
| --------------- | ------------------------------------------------------------ | -------- | ------------------------ |
| **函数原型**    | short   EMIO_ Get_Connected_Station_Type(unsigned short Station_Number); |          |                          |
| **说明**        | 根据从站模块的站点ID序号 Station_Number获取并返回该模块的类型。类型定义如下：(  0 : StationTypeIO2416 ) ( 1 : StationTypeIO4832 ) |          |                          |
| **原型参数**    |                                                              |          |                          |
| **类型**        | **名称**                                                     | **类型** | **说明**                 |
| unsigned short  | Station_Number                                               | 输入     | 指定从站模块的站点ID序号 |
| **C++示例**     | //首先获取已经实际连接上的从站模块的总数目  <br />unsigned short uiStationNums = EMIO_Get_Connected_Station_Nums();  <br />//根据从站模块的总数目分配存储所有从站类型的数组  <br />unsigned short* puiStationType = new unsigned short[uiStationNums];  for(unsigned short idx=0;  idx<uiStationNums; idx++) {         <br />//根据从站模块的站点ID序号 Station_Number获取并返回该模块的类型。      puiStationType[idx] =  EMIO_ Get_Connected_Station_Type (idx); <br />}  <br />delete   puiStationType; |          |                          |
| **C#** **示例** | ushort    uiStationNums =  EMIO.EMIO_Get_Connected_Station_Nums();  ushort[] puiStationType = new ushort[uiStationNums];  <br />for(ushort  idx=0; idx<uiStationNums; idx++) <br />{          <br />puiStationType[idx] = EMIO.EMIO_Get_Connected_Station_Type(idx);   <br />} |          |                          |

### 3.1.4 EMIO_Open()

打开总线从站模块。

|                  | **EMIO_Open**                                                |          |                                                              |
| ---------------- | ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| **函数原型**     | short   EMIO_Open(unsigned short Connection_Numbers, unsigned short  *Station_Types); |          |                                                              |
| **说明**         | 打开并连接指定数目 Connection_Numbers和指定模块类型 Station_Types数组的总线从站模块 |          |                                                              |
| **原型参数**     |                                                              |          |                                                              |
| **类型**         | **名称**                                                     | **类型** | **说明**                                                     |
| unsigned  short  | Connection_Numbers                                           | 输入     | 指定需要打开的所有从站模块的总数目。  注意这个总数目不一定与实际连接的所有从站模块的总数目相同，最好由 EMIO_  Get_Connected_Station_Nums()获取实际连接上的从站模块的总数目 |
| unsigned  short* | Station_Types                                                | 输入     | 指定需要打开的所有从站模块的类型数组指针                     |
| **C++示例**      | unsigned  short iStationNums = 0;  <br />//这时还不知道实际连接的从站模块数目，预定义56个  <br />unsigned  short iSationTypes[56] = {0};  <br />//获取所有已经实际连接上的从站模块的总数目及其类型数组  <br />short  siRtn = EMIO_Get_Connected_Stations(&iStationNums, iSationTypes);  <br />//打开所有从站模块  <br />siRtn  = EMIO_Open(iStationNums, iSationTypes); |          |                                                              |
| **C#** **示例**  | ushort   Station_Nums = 0;  ushort[] Station_Types = new ushort[56];  //获取所有已经实际连接上的从站模块的总数目及其类型数组  short siRtn  = EMIO.EMIO_Get_Connected_Stations(ref Station_Nums,  ref Station_Types[0]);  //打开所有从站模块  siRtn = EMIO.EMIO_Open(Station_Nums, ref  Station_Types[0]); |          |                                                              |

### 3.1.5 EMIO_OpenEx()

打开总线从站模块扩展。

|                 | **EMIO_OpenEx**                                              |          |                                                              |
| --------------- | ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| **函数原型**    | short   EMIO_OpenEx(unsigned short Connection_Numbers , unsigned short  *Station_Numbers, unsigned short *Station_Types); |          |                                                              |
| **说明**        | 打开并连接指定数目  Connection_Numbers，指定从站模块的站点ID序号Station_Numbers数组，指定模块类型 Station_Types数组的总线从站模块。 |          |                                                              |
| **原型参数**    |                                                              |          |                                                              |
| **类型**        | **名称**                                                     | **类型** | **说明**                                                     |
| unsigned short  | Connection_Numbers                                           | 输入     | 指定需要打开的所有从站模块的总数目。  注意这个总数目不一定与实际连接的所有从站模块的总数目相同，最好由 EMIO_ Get_Connected_Station_Nums()获取实际连接上的从站模块的总数目。 |
| unsigned short* | Station_Numbers                                              | 输入     | 所有从站模块的站点ID序号数组指针                             |
| unsigned short* | Station_Types                                                | 输入     | 所有从站模块的类型数组指针                                   |
| **C++示例**     | //指定需要打开2个从站模块  <br />unsigned short iStationNums = 2; <br />//指定从站站点ID序号  unsigned short iSationTypes[2] =  {StationTypeIO2416，StationTypeIO4832};<br />unsigned short iSationNumbers[2] = {0，1};  //打开2个站点号分别为 {0，1},类型分别为  //{StationTypeIO2416,StationTypeIO4832}的从站模块  <br />short siRtn = EMIO_OpenEx(iStationNums, iSationNumbers, iSationTypes); |          |                                                              |
| **C#** **示例** | //指定需要打开2个从站模块<br />ushort  Station_Nums  = 2;  <br /> //指定从站站点ID序号<br />ushort[]  Station_Numbers = new ushort[]{0,1};  <br />//指定从站站点类型  ushort[]  Station_Types  = new ushort[] {  (ushort)StationType.StationTypeIO2416, (ushort)StationType.StationTypeIO4832  };  // 打开总线从站模块<br />ushort   siRtn =  EMIO.EMIO_OpenEx(Station_Nums, ref Station_Numbers[0], ref Station_Types[0]); |          |                                                              |

### 3.1.6 EMIO_Close()

关闭总线从站模块。

|                 | **EMIO_Close**                   |
| --------------- | -------------------------------- |
| **函数原型**    | short   EMIO_Close();            |
| **说明**        | 关闭总线上所有从站模块。         |
| **C++示例**     | short  siRtn = EMIO_Close();     |
| **C#** **示例** | short siRtn = EMIO.EMIO_Close(); |

 

 

 

 

 

 

 

 

 

 

 

 

 

## 3.2 模块通用数字输入输出函数

### 3.2.1 EMIO_Get_Input()

获取指定站点的数字输入逻辑状态。

|                    | **EMIO_Get_Input**                                           |          |                                           |
| ------------------ | ------------------------------------------------------------ | -------- | ----------------------------------------- |
| **函数原型**       | short   EMIO_Get_Input(unsigned long *All_Input_Logic1, unsigned long  *All_Input_Logic2, unsigned short Station_Number); |          |                                           |
| **说明**           | 获取指定站点ID序号Station_Number从站模块的所有数字输入状态并返回到 All_Input_Logic1(Input31~  Input0)和 All_Input_Logic2(Input47~ Input32)。注意：返回值是按**位**对应的，如返回65536即0xffff（二进制1111 1111 1111 1111）即16个DI均为1，16个LED灯均为熄灭状态。 |          |                                           |
| **原型参数**       |                                                              |          |                                           |
| **类型**           | **名称**                                                     | **类型** | **说明**                                  |
| unsigned long***** | All_Input_Logic1                                             | 输出     | 按**位**返回数字输入状态(0 ~0xffffffff)。 |
| unsigned long***** | All_Input_Logic2                                             | 输出     | 按**位**返回数字输入状态(0 ~0xffffffff)。 |
| unsigned  short    | Station_Number                                               | 输入     | 从站模块的站点ID序号。                    |
| **C++示例**        | //获取站点号 gStation_Number[0]的EIO2416所有数字输入DI状态unsigned  long  All_Input_Logic1 =  All_Input_Logic2 = 0;  short siRtn =  0;    <br />//All_Input_Logic1(DI31  ~ DI0)和  All_Input_Logic2( DI47~  DI32)按**位**对应。  <br />siRtn =  EMIO_Get_Input  (  & All_Input_Logic1  ,& All_Input_Logic2  , gStation_Number[0] ); |          |                                           |
| **C#** **示例**    | //获取站点号  gStation_Number[0]的EIO2416所有数字输入DI状态uint AllOutputLogic1=0,  AllOutputLogic2 = 0;  short  siRtn =  0;    //All_Input_Logic1(DI31 ~ DI0)和 All_Input_Logic2( DI47~   DI32)按**位**对应。  <br />siRtn = EMIO.EMIO_Get_Input(ref  AllOutputLogic1, ref AllOutputLogic2, gStation_Numbers[0]); |          |                                           |

### 3.2.2 EMIO_Get_Input_Bit()

获取指定输入位和指定站点的数字输入位逻辑状态。

|                  | **EMIO_Get_ Input _Bit**                                     |          |                                    |
| ---------------- | ------------------------------------------------------------ | -------- | ---------------------------------- |
| **函数原型**     | short   EMIO_Get_ Input _Bit ( unsigned short  Bit_Input_Number, unsigned short *Bit_Input_Logic, unsigned short  Station_Number  ); |          |                                    |
| 说明             | 获取指定输入位Bit_Input_Number和指定站点ID序号Station_Number从站模块,的输入逻辑状态 Bit_Input_Logic。<br />注意：输入位Bit_Input_Number 是按值对应设输入的，如值为15即获取DI 15操作。 |          |                                    |
| **原型参数**     |                                                              |          |                                    |
| **类型**         | **名称**                                                     | **类型** | **说明**                           |
| unsigned  short  | Bit_Input_Number,                                            | 输入     | 按值指定数字输入位(0 ~ 31)。       |
| unsigned  short* | Bit_Input_Logic                                              | 输出     | 0:   LED灯亮状态  1:   LED灯熄状态 |
| unsigned  short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。             |
| **C++示例**      | unsigned   short Bit_Logic = 0;   short  siRtn = 0;  <br />//获取站点号  gStation_Number[0]的 EIO2416的DI15的输入状态 <br /> siRtn  = EMIO_Get_Input_Bit (15,  &Bit_Logic, gStation_Number[0]);  <br />//设置站点号  gStation_Number[0]的 EIO2416的DI0的输入状态  <br />siRtn  =  EMIO_Get_Input_Bit (0,   &Bit_Logic,,   gStation_Number[0]);  <br />//设置站点号  gStation_Number[1]的 EIO4832的DI31的输入状态  <br />siRtn  =  EMIO_Get_Input_Bit ( 31,  &Bit_Logic, gStation_Number[1] );  <br />//设置站点号  gStation_Number[1]的 EIO4832 的DI1的输入状态  <br />siRtn  =  EMIO_Get_Input_Bit ( 1,  &Bit_Logic, gStation_Number[1] ); |          |                                    |
| **C#** **示例**  | ushort  Bit_Logic = 0;  short siRtn = 0;  <br />//获取站点号 gStation_Number[0]的 EIO2416的DI15的输入状态  <br />siRtn = EMIO.EMIO_Get_Input_Bit(15, ref   Bit_Logic ,gStation_Numbers[0]);  <br />//设置站点号 gStation_Number[1]的 EIO4832的DI31的输入状态  siRtn = EMIO.EMIO_Get_Input_Bit(31, ref   Bit_Logic ,gStation_Numbers[1]); |          |                                    |

 

### 3.2.3 EMIO_Get_Output()

获取指定站点的数字输出逻辑状态。

|                 | **EMIO_Get_Output**                                          |          |                                   |
| --------------- | ------------------------------------------------------------ | -------- | --------------------------------- |
| **函数原型**    | short   EMIO_Get_Output(unsigned long*   All_Output_Logic, unsigned  short Station_Number); |          |                                   |
| **说明**        | 获取指定站点ID序号Station_Number从站模块的数字输出状态并返回到All_Output_Logic。<br />注意：返回值是按**位**对应的，如返回65536即0xffff（二进制1111 1111 1111 1111）即16个DO均为1，16个LED灯均为熄灭状态。 |          |                                   |
| **原型参数**    |                                                              |          |                                   |
| **类型**        | **名称**                                                     | **类型** | **说明**                          |
| unsigned long   | All_Output_Logic                                             | 输出     | 返回数字输出状态(0 ~0xffffffff)。 |
| unsigned  short | Station_Number                                               | 输入     | 从站模块的站点ID序号。            |
| **C++示例**     | unsigned long All_Output_Logic = 0;    short siRtn = 0;  <br />//获取站点号 gStation_Numbers[0]的EIO2416输出状态到 All_Output_Logic  <br />//如All_Output_Logic = 0xfffe  EIO2416 DO0状态为0，DO1-DO15状态为1  <br />siRtn = EMIO_Get_Output(  &All_Output_Logic , gStation_Numbers[0]  );  <br />//获取站点号 gStation_Numbers[1]的EIO4832输出状态到 All_Output_Logic  <br />//如All_Output_Logic=0xfffffffe  EIO4832 DO0状态为0，DO1-DO31状态为1  <br />siRtn = EMIO_Get_Output(  &All_Output_Logic , gStation_Numbers[1]  ); |          |                                   |
| **C#** **示例** | uint  AllOutputLogic = 0;    short  siRtn = 0;  <br />//获取站点号 gStation_Numbers[0]的EIO2416输出状态到 All_Output_Logic  <br />//如All_Output_Logic =  0xfffe  EIO2416 DO0状态为0，DO1-DO15状态为1  <br />siRtn  = EMIO.EMIO_Get_Output(ref AllOutputLogic, gStation_Numbers[0]);  <br />//获取站点号 gStation_Numbers[1]的EIO4832输出状态到 All_Output_Logic  <br />//如All_Output_Logic=0xfffffffe   EIO4832 DO0状态为0，DO1-DO31状态为1  <br />siRtn  = EMIO.EMIO_Get_Output(ref  AllOutputLogic, gStation_Numbers[1]); |          |                                   |
|                 |                                                              |          |                                   |

 

 

### 3.2.4 EMIO_Get_Output_Bit()

获取指定输出位和指定站点的数字输出位逻辑状态。

|                  | **EMIO_Get_Output_Bit**                                      |          |                                    |
| ---------------- | ------------------------------------------------------------ | -------- | ---------------------------------- |
| **函数原型**     | short   EMIO_Get_Output_Bit (unsigned short Bit_Output_Number, unsigned short*  Bit_Output_Logic, unsigned short  Station_Number ); |          |                                    |
| **说明**         | 获取指定输出位 Bit_Output_Number和指定站点ID序号Station_Number的从站模块的输出逻辑状态Bit_Output_Logic  。<br />注意：指定输出位Bit_Output_Number是按**值**对应的，如值为15即获取DO15状态。 |          |                                    |
| **原型参数**     |                                                              |          |                                    |
| **类型**         | **名称**                                                     | **类型** | **说明**                           |
| unsigned  short  | Bit_Output_Number,                                           | 输入     | 按值指定数字输出位(0 ~ 31)。       |
| unsigned  short* | Bit_Output_Logic                                             | 输出     | 0:   LED灯亮状态  1:   LED灯熄状态 |
| unsigned  short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。             |
| **C++示例**      | unsigned  short  Bit_Logic = 0;    short siRtn = 0;  <br />//获取站点号 gStation_Number[0]的 EIO2416的DO15的输入状态  <br />siRtn =  EMIO_Get_Output_Bit (15, &Bit_Logic,  gStation_Numbers[0]);  //获取站点号 gStation_Number[0]的 EIO2416的DO0的输入状态  <br />siRtn =  EMIO_Get_Output_Bit (0,  &Bit_Logic,,  gStation_Numbers[0]);  //获取站点号 gStation_Number[1]的 EIO4832的DO31的输入状态  <br />siRtn =  EMIO_Get_Output_Bit ( 31, &Bit_Logic, gStation_Numbers[1] );  //获取站点号 gStation_Number[1]的 EIO4832 的DO1的输入状态  <br />siRtn =  EMIO_Get_Output_Bit ( 1,  &Bit_Logic, gStation_Numbers[1] ); |          |                                    |
| **C#** **示例**  | ushort   Bit_Logic = 0; short siRtn = 0;  <br />//获取站点号 gStation_Number[0]的 EIO2416的DO15的输入状态  EMIO.EMIO_Get_Output_Bit(15,  ref  Bit_Logic, gStation_Numbers[0]);  //获取站点号 gStation_Number[1]的 EIO4832的DO31的输入状态  EMIO.EMIO_Get_Output_Bit(31,  ref  Bit_Logic, gStation_Numbers[1]); |          |                                    |

 

### 3.2.5 EMIO_Set_Output()

设置指定站点的数字输出逻辑。

|                  | **EMIO_Set_Output**                                          |          |                                               |
| ---------------- | ------------------------------------------------------------ | -------- | --------------------------------------------- |
| **函数原型**     | short EMIO_Set_Output(unsigned long All_Output_Logic, unsigned short Station_Number); |          |                                               |
| **说明**         | 设置指定站点ID序号Station_Number从站模块的数字IO输出状态 All_Output_Logic。<br />注意： All_Output_Logic是按**位**对应设输出的，如16个DO均为1即0xffff（二进制1111 1111 1111 1111）其值为65536，熄灭16个LED灯。 |          |                                               |
| **原型参数**     |                                                              |          |                                               |
| **类型**         | **名称**                                                     | **类型** | **说明**                                      |
| unsigned long    | All_Output_Logic                                             | 输入     | 按**位**设置的数字IO输出状态(0 ~0xffffffff)。 |
| unsigned short   | Station_Number                                               | 输入     | 从站模块的站点ID序号。                        |
| **C++示例**      | short siRtn = 0;  <br />//设置站点号 gStation_Number[0]的 EIO2416的16DO输出为0 点亮LED灯  <br />siRtn  = EMIO_Set_Output( 0x0,     gStation_Numbers[0] );  <br />//设置站点号 gStation_Number[0]的 EIO2416的16DO输出为1 熄灭LED灯  <br />siRtn  = EMIO_Set_Output( 0xffff,    gStation_Numbers[0] );  <br />//设置站点号 gStation_Number[1]的 EIO4832 DO0输出为0 DO1-DO31输出为1  <br />siRtn  = EMIO_Set_Output( 0xfffffffe, gStation_Numbers[1] );  <br />//设置站点号 gStation_Number[1]的 EIO4832 32DO输出为1 熄灭LED灯  siRtn  = EMIO_Set_Output( 0xffffffff,   gStation_Numbers[1] ); |          |                                               |
| **C#**  **示例** | short siRtn = 0;  <br />//设置站点号 gStation_Number[0]的 EIO2416的16DO输出为0 点亮LED灯  <br />siRtn = EMIO.EMIO_Set_Output(0x0,    gStation_Numbers[0]);  <br />//设置站点号 gStation_Number[0]的 EIO2416的16DO输出为1 熄灭LED灯  <br />siRtn = EMIO.EMIO_Set_Output(0xffff,   gStation_Numbers[0]);  <br />//设置站点号 gStation_Number[1]的 EIO4832 DO0输出为0，DO1-DO31输出为1  <br />siRtn = EMIO.EMIO_Set_Output(0xfffffffe, gStation_Numbers[1]);  <br />//设置站点号 gStation_Number[1]的 EIO4832 32DO输出为1 熄灭LED灯  <br />siRtn = EMIO.EMIO_Set_Output(0xffffffff,  gStation_Numbers[1]); |          |                                               |
|                  |                                                              |          |                                               |

### 3.2.6 EMIO_Set_Output_Bit()

设置指定输出位和指定站点的数字输出位逻辑。

|                 | **EMIO_Set_Output_Bit**                                      |          |                              |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------------- |
| **函数原型**    | short   EMIO_Set_Output_Bit (unsigned short Bit_Output_Number, unsigned short  Bit_Output_Logic, unsigned short  Station_Number ); |          |                              |
| **说明**        | 设置指定输出位 Bit_Output_Number和指定站点ID序号Station_Number的从站模块的输出逻辑 Bit_Output_Logic 。<br />注意：指定输出位 Bit_Output_Number是按**值**对应设输出的，比如值为15即对DO15操作。 |          |                              |
| **原型参数**    |                                                              |          |                              |
| **类型**        | **名称**                                                     | **类型** | **说明**                     |
| unsigned short  | Bit_Output_Number,                                           | 输入     | 按值指定数字输出位(0 ~ 31)。 |
| unsigned short  | Bit_Output_Logic                                             | 输入     | 0:  点亮LED灯  1:  熄灭LED灯 |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。       |
| **C++示例**     | short  siRtn = 0;  <br />//设置站点号 gStation_Numbers[0]的 EIO2416的DO15输出为0 点亮LED灯  siRtn =  EMIO_Set_Output_Bit  (15, 0, gStation_Numbers[0]);  <br />//设置站点号 gStation_Numbers[0]的 EIO2416的DO0输出为1 熄灭LED灯  siRtn =  EMIO_Set_Output_Bit  (0,  1,  gStation_Numbers[0]);  <br />//设置站点号 gStation_Numbers[1]的 EIO4832的DO31输出为0 点亮LED灯  siRtn =  EMIO_Set_Output_Bit  (31, 0, gStation_Numbers[1] );  <br />//设置站点号 gStation_Numbers[1]的 EIO4832 的DO1输出为1 熄灭LED灯  siRtn =  EMIO_Set_Output_Bit  (1,  1,  gStation_Numbers[1]  ); |          |                              |
| **C#** **示例** | short siRtn = 0;  <br />//设置站点号 gStation_Numbers[0]的 EIO2416的DO15输出为0 点亮LED灯  <br />siRtn = EMIO.EMIO_Set_Output_Bit(15,  0,  gStation_Numbers[0]  );  <br />//设置站点号 gStation_Numbers[1]的 EIO4832的DO31输出为0 点亮LED灯  <br />siRtn = EMIO.EMIO_Set_Output_Bit (31,  0, gStation_Numbers[1] ); |          |                              |

### 3.2.7 EMIO_Inv_Output_Bit()

反向设置指定输出位和指定站点的数字输出位逻辑。

|                 | **EMIO_Inv_Output_Bit**                                      |          |                                    |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------------------- |
| **函数原型**    | short    EMIO_Inv_Output_Bit (unsigned  short Bit_Output_Number, unsigned short Station_Number ); |          |                                    |
| **说明**        | 反向设置指定输出位 Bit_Output_Number和指定站点ID序号Station_Number的从站模块的数字输出状态。<br />注意：反向输出位Bit_Output_Number是按**值**对应设输出的，如值为15即对DO15操作。 |          |                                    |
| **原型参数**    |                                                              |          |                                    |
| **类型**        | **名称**                                                     | **类型** | **说明**                           |
| unsigned  short | Bit_Output_Number,                                           | 输入     | 按值指定反向数字输出位(0 ~ 31)。。 |
| unsigned  short | Station_Number                                               | 输入     | 从站模块的站点ID序号。             |
| **C++示例**     | short siRtn = 0;  <br />//反向站点号 gStation_Numbers[0]的 EIO2416的DO15的输出 原LED灯亮变灭  <br />siRtn =  EMIO_Inv_Output_Bit (15,   gStation_Numbers[0]);  <br />//反向站点号 gStation_Numbers[1]的 EIO4832的DO31的输出 原LED灯灭变亮  <br />siRtn =  EMIO_Inv_Output_Bit (31,   gStation_Numbers[1]); |          |                                    |
| **C#** **示例** | short  siRtn = 0;  <br />//反向站点号 gStation_Numbers[0]的 EIO2416的DO15的输出 原LED灯亮变灭  <br />siRtn  =  EMIO.EMIO_Inv_Output_Bit (15,   gStation_Numbers[0]);  <br />//反向站点号 gStation_Numbers[1]的 EIO4832的DO31的输出 原LED灯灭变亮  <br />siRtn  =  EMIO.EMIO_Inv_Output_Bit (31,   gStation_Numbers[1]); |          |                                    |

 

 

 

 

 

## 3.3 模块实用函数

### 3.3.1 EMIO_Get_First_Error_Message()

获取系统出现的第一个错误信息。

|                 | **EMIO_Get_First_Error_Message**                             |          |                              |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------------- |
| **函数原型**    | short    EMIO_Get_First_Error_Message( LPTSTR Error_Message, unsigned  short  Unicode = 1  ); |          |                              |
| **说明**        | 根据指定字符集类型获取系统出现的第一个错误信息字符数组。Unicode类型定义如下：( 0 : 非Unicode  )  ( 1 : Unicode ) |          |                              |
| **原型参数**    |                                                              |          |                              |
| **类型**        | **名称**                                                     | **类型** | **说明**                     |
| LPTSTR          | Error_Message                                                | 输出     | 返回系统出现的第一个错误信息 |
| unsigned short  | Unicode                                                      | 输入     | 程序是否使用Unicode字符集    |
| **C++示例**     | TCHAR  cErrMessage[256];  <br />short  siRtn =  EMIO_Get_First_Error_Message ( cErrMessage , 0 ); |          |                              |
| **C#** **示例** | StringBuilder ErrorMsg = new StringBuilder("",  100);  <br />short siRtn = EMIO. EMIO_Get_First_Error_Message ( ErrorMsg, 0 ); |          |                              |

 

### 3.3.2 EMIO_Get_Last_Error_Message()

获取系统出现的最后一个错误信息。

|                 | **EMIO_Get_Last_Error_Message**                              |          |                                |
| --------------- | ------------------------------------------------------------ | -------- | ------------------------------ |
| **函数原型**    | short    EMIO_Get_Last_Error_Message(  LPTSTR Error_Message, unsigned short Unicode = 1  ); |          |                                |
| **说明**        | 根据指定字符集类型获取系统出现的最后一个错误信息字符数组。Unicode类型定义如下：( 0 : 非Unicode  )  ( 1 : Unicode ) |          |                                |
| **原型参数**    |                                                              |          |                                |
| **类型**        | **名称**                                                     | **类型** | **说明**                       |
| LPTSTR          | Error_Message                                                | 输出     | 返回系统出现的最后一个错误信息 |
| unsigned short  | Unicode                                                      | 输入     | 程序是否使用Unicode字符集      |
| **C++示例**     | TCHAR  cErrMessage[256];  <br />short  siRtn =  EMIO_Get_Last_Error_Message ( cErrMessage , 0 ); |          |                                |
| **C#** **示例** | StringBuilder ErrorMsg = new  StringBuilder("", 100);  <br />short siRtn = EMIO. EMIO_Get_Last_Error_Message ( ErrorMsg, 0 ); |          |                                |

 

### 3.3.3 EMIO_Get_Error_Message()

根据指定错误代码和指定字符集获取具体错误信息。

|                 | **EMIO_Get_Error_Message**                                   |          |                           |
| --------------- | ------------------------------------------------------------ | -------- | ------------------------- |
| **函数原型**    | short    EMIO_Get_Error_Message ( LPTSTR  Error_Message, short Error_Code,  unsigned short  Unicode = 1  ); |          |                           |
| **说明**        | 根据错误代码 Error_Code和字符集 Unicode获取具体错误信息字符数组。Unicode类型定义如下：( 0 : 非Unicode  )  ( 1 : Unicode ) |          |                           |
| **原型参数**    |                                                              |          |                           |
| **类型**        | **名称**                                                     | **类型** | **说明**                  |
| LPTSTR          | Error_Message                                                | 输出     | 返回具体的错误信息        |
| short           | Error_Code                                                   | 输入     | 具体的错误代码            |
| unsigned short  | Unicode                                                      | 输入     | 程序是否使用Unicode字符集 |
| **C++示例**     | TCHAR cErrMessage[256];  <br />short siRtn = EMIO_Get_Error_Message(  cErrMessage , -18, 0 ); |          |                           |
| **C#** **示例** | StringBuilder  ErrorMsg = new StringBuilder("", 100);  <br />short  siRtn = EMIO.EMIO_Get_Error_Message( ErrorMsg, -18, 0 ); |          |                           |

 

### 3.3.4 EMIO_Get_SN()

获取指定站点的硬件序列号信息。

|                 | **EMIO_Get_SN**                                              |          |                                  |
| --------------- | ------------------------------------------------------------ | -------- | -------------------------------- |
| 函数原型        | short    EMIO_Get_SN ( INT64  *Serial_Number, unsigned short Station_Number); |          |                                  |
| **说明**        | 获取指定站点 Station_Number的硬件序列号信息返回到 Serial_Number变量中。 |          |                                  |
| **原型参数**    |                                                              |          |                                  |
| **类型**        | **名称**                                                     | **类型** | **说明**                         |
| INT64 *         | Serial_Number                                                | 输出     | 返回硬件序列号，维一的64位硬件码 |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。           |
| **C++示例**     | INT64  lSN =0;  <br />short  siRtn =  EMIO_Get_SN(&lSN,  Station_Numbers[0]); |          |                                  |
| **C#** **示例** | Int64 lSN = 0;  <br />short siRtn = EMIO.EMIO_Get_SN(ref lSN,  gStation_Numbers[0]); |          |                                  |

 

### 3.3.5 EMIO_Get_SN_Text()

获取指定站点的硬件序列号信息字符数组。

|                 | **EMIO_Get_SN_Text**                                         |          |                                  |
| --------------- | ------------------------------------------------------------ | -------- | -------------------------------- |
| 函数原型        | short    EMIO_Get_SN_Text (LPTSTR  Serial_Number, unsigned short Station_Number, unsigned short   Unicode = 1); |          |                                  |
| **说明**        | 获取指定站点 Station_Number的硬件序列号返回到 Serial_Number字符数组中。 |          |                                  |
| **原型参数**    |                                                              |          |                                  |
| **类型**        | **名称**                                                     | **类型** | **说明**                         |
| LPTSTR          | Serial_Number                                                | 输出     | 返回硬件序列号，维一的64位硬件码 |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。           |
| unsigned short  | Unicode                                                      | 输入     | 程序是否使用Unicode字符集        |
| **C++示例**     | TCHAR pszStationSN[MAX_PATH] = {0};   <br />short siRtn =   EMIO_Get_SN_Text ( pszStationSN , Station_Numbers[0] ); |          |                                  |
| **C#** **示例** | StringBuilder  SN = new StringBuilder("",  100);  <br />short  siRtn =  EMIO.EMIO_Get_SN_Text(SN, 0); |          |                                  |

### 3.3.6 EMIO_Get_Station_Info()

获取指定站点的站点信息。

|                 | **EMIO_Get_Station_Info**                                    |          |                             |
| --------------- | ------------------------------------------------------------ | -------- | --------------------------- |
| 函数原型        | short  EMIO_Get_Station_Info (unsigned long * Station_Info ,  unsigned short Station_Number); |          |                             |
| **说明**        | 获取指定站点 Station_Number的站点信息返回到  Station_Info 数组中。 |          |                             |
| **原型参数**    |                                                              |          |                             |
| **类型**        | **名称**                                                     | **类型** | **说明**                    |
| unsigned long * | Station_Info                                                 | 输出     | 返回站点信息(类型 固件版本) |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。      |
| **C++示例**     | unsigned  long ulStationInfo = 0;  <br />short  siRtn = EMIO_Get_Station_Info( ulStationInfo  , Station_Numbers[0] ); |          |                             |
| **C#** **示例** | uint   ulStationInfo = 0;  <br />short  siRtn = EMIO.EMIO_Get_Station_Info(ref  ulStationInfo, gStation_Numbers[0]); |          |                             |

 

### 3.3.7 EMIO_Get_Dll_Version()

获取软件动态库版本信息。

|                 | **EMIO_Get_Dll_Version**                                     |          |                        |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------- |
| 函数原型        | short   EMIO_Get_Dll_Version (LPTSTR DllVersion);            |          |                        |
| **说明**        | 获取软件动态库版本信息返回到 DllVersion 字符数组中。         |          |                        |
| **原型参数**    |                                                              |          |                        |
| **类型**        | **名称**                                                     | **类型** | **说明**               |
| LPTSTR          | DllVersion                                                   | 输出     | 返回软件动态库版本信息 |
| **C++示例**     | TCHAR pszFileVersion[MAX_PATH] = {0};   <br />short  siRtn =  EMIO_Get_Dll_Version(pszFileVersion); |          |                        |
| **C#** **示例** | StringBuilder  Version = new StringBuilder("", 100);  <br />short  siRtn =  EMIO.EMIO_Get_Dll_Version(Version); |          |                        |

 

### 3.3.8 EMIO_Get_Language()

获取软件动态库错误信息语言类型。

|                 | **EMIO_Get_Language**                                        |      |
| --------------- | ------------------------------------------------------------ | ---- |
| 函数原型        | short    EMIO_Get_Language ();                               |      |
| **说明**        | 获取并返回软件动态库错误信息语言类型。(  0 : 简体中文 ) ( 1 : 英文 ) 默认中文 |      |
| **C++示例**     | short  siLanguage =  EMIO_Get_Language();                    |      |
| **C#** **示例** | short  siLanguage =  EMIO.EMIO_Get_Language();               |      |
|                 |                                                              |      |

 

### 3.3.9 EMIO_Set_Language()

设置软件动态库错误信息语言类型。

|                 | **EMIO_Set_Language**                                        |          |                  |
| --------------- | ------------------------------------------------------------ | -------- | ---------------- |
| 函数原型        | short    EMIO_Set_Language ( short Language );               |          |                  |
| **说明**        | 设置软件动态库错误信息语言类型。(  0 : 简体中文 ) ( 1 : 英文 ) |          |                  |
| **原型参数**    |                                                              |          |                  |
| **类型**        | **名称**                                                     | **类型** | **说明**         |
| short           | Language                                                     | 输入     | 错误信息语言类型 |
| **C++示例**     | short siRtn =  EMIO_Set_Language(0);                         |          |                  |
| **C#** **示例** | short  siRtn =  EMIO.EMIO_Set_Language(1);                   |          |                  |

 

### 3.3.10 EMIO_Get_Process_Type()

获取进程的类型。

|                 | **EMIO_Get_** **Process_Type**                           |
| --------------- | -------------------------------------------------------- |
| 函数原型        | short   EMIO_Get_Process_Type ();                        |
| **说明**        | 获取并返回进程的类型。(0  : 32位进程 ) (  1 : 64位进程 ) |
| **C++示例**     | short  siProcessType =  EMIO_Get_Process_Type();         |
| **C#** **示例** | short  siProcessType =  EMIO. EMIO_Get_Process_Type();   |

 

### 3.3.11 EMIO_Register_Callback_Event()

注册断线，重连或断电回调事件。

|                       | **EMIO_Register_Callback_Event**                             |          |                                                              |
| --------------------- | ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| 函数原型              | short    EMIO_Register_Callback_Event ( PFEMIO_Callback_Event  CallbackFunc,  unsigned short EventType  ); |          |                                                              |
| **说明**              | 注册断线或重连回调事件。                                     |          |                                                              |
| **原型参数**          |                                                              |          |                                                              |
| **类型**              | **名称**                                                     | **类型** | **说明**                                                     |
| PFEMIO_Callback_Event | CallbackFunc                                                 | 输入     | 回调事件函数指针。                                           |
| unsigned short        | EventType                                                    | 输入     | 回调事件类型。  0: YSEventStationsDisconnected   1: YSEventStationsInterrupReconnected  2: YSEventStationsPowerOffReconnected |
| **C++示例**           | //1.自定义一个被回调函数  <br />short  WINAPI CallbackEventStationsDisconnected()  <br />{    CString sDisconnected=  (CTime::GetCurrentTime()).Format(_T("模块已断线  %Y%m%d %H%M%S") );    return 0;  <br />}  <br />//2.在打开从站模块后  注册被回调函数及其类型  EMIO_Register_Callback_Event(CallbackEventStationsDisconnected,  YSEventStationsDisconnected); |          |                                                              |
| **C#** **示例**       | //1.自定义一个事件处理函数  <br />public static void  StationsDisconnectedEventProc()  <br />{  String sDisconnected ="模块已断线";  } <br /> //2.声明并新建一个事件委托及其处理函数  <br />EMIO_Callback_Event  StationsDisconnectedEvent  = new EMIO. EMIO_Callback_Event ( StationsDisconnectedEventProc );  <br />//3.在打开从站模块后 注册事件委托及其类型  EMIO.EMIO_Register_Callback_Event(  StationsDisconnectedEvent , 0); |          |                                                              |

 

### 3.3.12 EMIO_Get_Disconnect_Counts()

获取网络掉线的次数。

|                 | **EMIO_Get_Disconnect_Counts**                         |
| --------------- | ------------------------------------------------------ |
| 函数原型        | short   EMIO_Get_Disconnect_Counts ();                 |
| **说明**        | 获取网络掉线的次数。                                   |
| **C++示例**     | short  uiDisCnts = EMIO_Get_Disconnect_Counts();       |
| **C#** **示例** | short  uiDisCnts = EMIO. EMIO_Get_Disconnect_Counts(); |

 

### 3.3.13 EMIO_Set_Disconnect_Counts()

设置网络掉线的次数。

|                 | **EMIO_Set_Disconnect_Counts**                               |          |                          |
| --------------- | ------------------------------------------------------------ | -------- | ------------------------ |
| 函数原型        | short   EMIO_Set_Disconnect_Counts (short  Disconnect_Counts ); |          |                          |
| **说明**        | 设置网络掉线的次数。                                         |          |                          |
| **原型参数**    |                                                              |          |                          |
| **类型**        | **名称**                                                     | **类型** | **说明**                 |
| short           | Disconnect_Counts                                            | 输入     | 设置网络掉线的次数，清零 |
| **C++示例**     | short siRtn  = EMIO_Set_Disconnect_Counts(0);                |          |                          |
| **C#** **示例** | short  siRtn  = EMIO. EMIO_Set_Disconnect_Counts(0);         |          |                          |

 

### 3.3.14 EMIO_Get_Interrup_Reconnect_Counts()

获取网络中断掉线后重新连接的次数。

|                 | **EMIO_Get_Interrup_Reconnect_Counts**                       |
| --------------- | ------------------------------------------------------------ |
| 函数原型        | short   EMIO_Get_Interrup_Reconnect_Counts ();               |
| **说明**        | 获取网络中断后重新连接的次数。                               |
| **C++示例**     | short uiInterrupReCnts =  EMIO_Get_Interrup_Reconnect_Counts(); |
| **C#** **示例** | short uiInterrupReCnts = EMIO.EMIO_Get_Interrup_Reconnect_Counts(); |

 

### 3.3.15 EMIO_Set_Interrup_Reconnect_Counts()

设置网络中断掉线后重新连接的次数。

|                 | **EMIO_Set_Interrup_Reconnect_Counts**                       |          |                                    |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------------------- |
| 函数原型        | short   EMIO_Set_Interrup_Reconnect_Counts ( short Interrup_Reconnect_Counts); |          |                                    |
| **说明**        | 设置网络中断掉线后重新连接的次数。                           |          |                                    |
| **原型参数**    |                                                              |          |                                    |
| **类型**        | **名称**                                                     | **类型** | **说明**                           |
| short           | Interrup_Reconnect_Counts                                    | 输入     | 设置网络中断掉线后重连的次数，清零 |
| **C++示例**     | short siRtn = EMIO_Set_Interrup_Reconnect_Counts(0);         |          |                                    |
| **C#** **示例** | short  siRtn = EMIO.EMIO_Set_Interrup_Reconnect_Counts(0);   |          |                                    |

 

### 3.3.16 EMIO_Get_PowerOff_Reconnect_Counts()

获取指定站点模块断电后重新连接的次数。

|                 | **EMIO_Get_PowerOff_Reconnect_Counts**                       |          |                        |
| --------------- | ------------------------------------------------------------ | -------- | ---------------------- |
| 函数原型        | short   EMIO_Get_PowerOff_Reconnect_Counts (unsigned short Station_Number); |          |                        |
| **说明**        | 获取指定站点模块断电后重新连接的次数。                       |          |                        |
| **原型参数**    |                                                              |          |                        |
| **类型**        | **名称**                                                     | **类型** | **说明**               |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。 |
| **C++示例**     | short uiReCnts = EMIO_Get_PowerOff_Reconnect_Counts(0);      |          |                        |
| **C#** **示例** | short uiReCnts  = EMIO.EMIO_Get_PowerOff_Reconnect_Counts(1); |          |                        |

 

### 3.3.17 EMIO_Set_PowerOff_Reconnect_Counts()

设置指定站点模块断电后重新连接的次数。

|                 | **EMIO_Set_PowerOff_Reconnect_Counts**                       |          |                                  |
| --------------- | ------------------------------------------------------------ | -------- | -------------------------------- |
| 函数原型        | short   EMIO_Set_PowerOff_Reconnect_Counts (short PowerOff_Reconnect_Counts ,  unsigned short Station_Number); |          |                                  |
| **说明**        | 设置指定站点模块断电后重新连接的次数。                       |          |                                  |
| **原型参数**    |                                                              |          |                                  |
| **类型**        | **名称**                                                     | **类型** | **说明**                         |
| short           | PowerOff_Reconnect_Counts                                    | 输入     | 设置站点模块断电后重新连接的次数 |
| unsigned short  | Station_Number                                               | 输入     | 从站模块的站点ID序号。           |
| **C++示例**     | short  siRtn = EMIO_Set_PowerOff_Reconnect_Counts(0,0);      |          |                                  |
| **C#** **示例** | short siRtn = EMIO.EMIO_Set_PowerOff_Reconnect_Counts(0,1);  |          |                                  |

 

# 第4章 常见问题FAQ

## 4.1 硬件常见FAQ

Q: 总线式系统架构是否可以同时用两个或多个网口连接并同时打开所有从站模块？

A: **不可以**！为保证通讯的实时及稳定性，同一时间段内只能打开一个网口串联的所有从站模块。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/411.png"/></div>

<p align="center">图4.1.1 总线式系统架构</p>

\-----------------------------------------------------------------------------------------------------------------

Q: NET_IN和NET_OUT口接入顺序可不可以接反？

A: **不可以**！如果API一直返回打开站点不成功，请先确认网线的接入顺序，必须严格按照从NET_IN口接入，串接的话从NET_OUT接出，如不串接，端回环接头必须接NET_OUT口。

\-----------------------------------------------------------------------------------------------------------------

Q: 可以不接终端回环接头么？

A: **不可以**！必须接终端回环接头。

(1). 不接终端回环接头, 返回打开站点不成功

(2). 接了终端回环接头, 打开站点成功后，拨掉回环头，报网络链接中断；重新插上后，恢复正常。

\-----------------------------------------------------------------------------------------------------------------

Q: 总线式系统架构最多可以串联多少个模块？

A: 为保证通讯周期1ms，总线式系统架构最多可以级联56个模块。以48DI32DO来算，最多总共可以控制80x56=4480点(2784DO/896DI) 。

\-----------------------------------------------------------------------------------------------------------------

Q: 如果级联少于56个模块，总线通讯周期会少于1ms么？

A: 不会，总线通讯周期依然是1ms，如果需要更改总线通讯周期，请联系厂商客制化 。

\-----------------------------------------------------------------------------------------------------------------

Q: 可以使用普通的非屏蔽网线么？

A: **不可以**！网络线缆的质量对通讯的稳定性有极其重要的作用，非屏蔽/普通/劣质网线容易引起网络断线及通讯不稳定。请使用厂商经过测试的配套超6类双屏蔽网线（CAT6e SFTP） 。

\-----------------------------------------------------------------------------------------------------------------

Q: API函数是否支持Linux和 Mac系统？

A: 目前暂时不支持，如果需要其他操作系统支持，请联系厂商客制化 。

\-----------------------------------------------------------------------------------------------------------------

Q: 电脑主站网口是否要设置固定IP地址？

A: **需要**！设置与模块连接的电脑主站网口为固定IP地址，由于Windows的网络接口特性，固定IP地址不仅能使通讯更加稳定，而且能加快网络断线与重连的速度。

<div align="center"><img src="https://raw.githubusercontent.com/yunshi-tech/EMIO/master/Images/412.png"/></div>

<p align="center">图4.1.2 设置网络连接固定IP地址</p>

## 4.2 软件常见FAQ

 

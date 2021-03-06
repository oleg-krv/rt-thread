# RT-Thread v3.0.2 Change log

## Platform

* Make sure the Object_Class to a fixed value
* Add `rt_device_create/destroy` API
* Add memory trace for small memory management algorithm for memory leak and overwritten.
* Add a first version of asynchronous I/O API
* Add cputime for high resolution counter
* Add pipe device functions in DeviceDrivers
* USB Host available in stm32f4 with mass storage class
* Add 'df' command in msh
* Update UI engine and add an example
* Split `clock_time` from pthreads and add a new clock id: `CLOCK_CPUTIME_ID`
* Enable IPv6 in lwIP 2.0.2 version
* Add memlog in logtrace
* Fix closesocket issue in dfs_net
* Fix IPv6 issue in NFS
* Update JFFS2 file system with new DFS API
* Fix the issue of stat "/.." of lwext4 (parai)
* Fix the fs type search issue in mkfs
* Fix the select issue in dfs_net

## Tools

* scons: add '--useconfig' command to use an exist config file
* scons: force to use g++ for link when enable `RT_USING_CPLUSPLUS` in GNU GCC configuration
* Enable package feature in Linux/MacOS host

## BSP

* Add NUC472 bsp (bluebear)
* Update SD/MMC driver for qemu-vexpress-A9
* Add keyboard/mouse driver for qemu-vexpress-a9
* Add ADC/I2C/Flash/PWM/RTC/smbus/SPI driver for apollo2 (Haleyl)
* Add I2C/LCD/Touch driver for i.MXRT1052-EVK
* Update SD/MMC driver for mini2440 (kuangdazzidd)
* Update simulator to adapt VC++ compiler
* Add USB host driver in stm32f4xx-HAL (uestczyh222)
* Update EMAC driver for IPv6 in stm32f40x/stm32f107
* Add stm32h743-nucleo bsp (polariss)

# RT-Thread v3.0.1 Change log

## Platform:

* Add mmap()/munmap() API for POSIX compatibility.
* Fix the filesystem_operation_table issue.
* Enhance USB stack for USB slave (HID/ECM/RNDIS/WINUSB or composite device);
* Enhance USB stack for USB host (HID/MSC etc);
* Fix memory leak issue when close a pipe.  
* Fix the romfs open issue;
* Add SoftAP device in Wi-Fi framework;
* Re-order the lwIP/ETH initialization;
* Add IPv6 options in Kconfig;
* Fix the module_id issue in _rt_thread_init;

## Tools:

* Add menuconfig for Linux/Mac platform: use `scons --memuconfig` to enable it;
* Add LIBS feature for IAR project;

## BSP:

* Enhance LPC54608 BSP for kinds of compiler;
* Add GPIO/I2C/SPI driver for Loongson 1C;
* Add csd cmd in sdcard driver of mini2440;
* Add SDIO/EMAC driver for qemu-vexpress-a9 bsp;
* Enable VC++ to compile simulator bsp;
* Add stm32f4xx-HAL bsp for kinds of STM32F4 series <User can use menuconfig to select chip>;
* Fix the PHY reset in stm32f429-apollo bsp;
* Add Audio/MMC/SLCD/Touch/USB slave/RTC/SPI/SFC Flash driver in Ingenic X1000 bsp;

# RT-Thread v3.0.0 Change log
## Platform:

* Add more POSIX features, for example poll/select, signal, termios etc.
* Add waitqueue for poll feature.
* Use fops for file operation. There are two ways to visit device object: rt_device_* API, the file API(open/read/write/close etc).
* Change the type of cmd from uint8_t to int in control interface.
* Add more C++ object for RT-Thread Kernel Object.
* Add wlan driver framework for wlan device operation.
* Integrate SFUD into RT-Thread to unify the operations of spi flash.
* Update lwIP to v2.0.2 version.

## Tools:

* Enable packages, with ENV tool.
* menuconfig & Kconfig.
* Add scons --dist for make a distribution for specified BSP.

## BSP:

* more MCU porting.

## IoT:

* put more IoT components as packages, for example, MQTT, CoAP, HTTP, TLS etc.

# RT-Thread v2.1.0 Change log

This release is the final release for RT-Thread v2.1.0 branch. This release has been delayed many time. After committed fh8620 and x1000 bsp, we are proud to announce this branch release of the official version.

The change log since last stable version:

## Kernel:

* Move the init component to the kernel.
* Fix the device open flag issue.
* Add assertion hook.
* Better application module support.
* Does not lock scheduler when invoking soft-timer timeout function.

## Board Support Package:

* fh8620, which is provided by Shanghai Fullhan Microelectronics Co., Ltd. It's a IP camera chip with ARM1176, 300MHz, 16KB I-Cache and 16kB D-Cache.
* x1000 bsp. The CPU is a XBurst CPU 1.0GHz, MIPS-based, from Ingenic Semiconductor Co.,Ltd.
* imx6sx bsp, only the Cortex-A9 core porting in the NXP i.MX6 solox. BTW, another full Kinetis series porting was created in rt-thread_fsl, which is maintained by NXP employee.
* lpc5410x bsp, only the Cortex-M4 core porting.
* ls1cdev bsp for Loogson1C board.
* dm365 bsp.
* nRF51822/nRF52832 bsp.
* stm32f7-disco bsp, the first ARM Cortex-M7 porting in RT-Thread.
* stm32f411-nucleo bsp.
* Add IAR compiler support in beaglebone bsp.

## Components:

* Add more socket fd operators in DFS with a virtual lwIP file system ops.
* Add CAN/Hardware Timer device drivers.
* Fix the SDIO issue to support sdio wifi device.
* Add eMMC support in SD/MMC device drivers;
* Fix the NAT configured enter reset issue in lwIP NAT.
* RTGUI come back, but as a UI engine for blend point/line/rect and bitmap etc.
* Add nanopb porting, a small code-size Protocol Buffers implementation;
* Add paho-mqtt porting, the Eclipse Paho MQTT C/C++ client for Embedded platforms;
* Update freetype to 2.5.4 version.
* Enhance msh for file operations.
* Split the exported commands of finsh shell to a standalone section: ".rodata.name"

# RT-Thread v2.1.0 beta版本更改说明

## BSP部分

* BeagleBone加入GPIO驱动；
* 京微雅格M7，更新驱动库并改进EMAC驱动程序；
* 新加入dm365移植（包括EMAC、GPIO、I2C、MMC/SD、SPI等驱动）；
* LPC4088加入EMC、硬件定时器、CAN驱动；
* 新加入龙芯1C，智龙v2开发板移植（包括多串口驱动）；
* 更改mini2440移植为applications/drivers等的目录方式；
* 更新simulator在MS VC++上的移植，处理好初始化代码工作，完善UART控制台驱动；
* 新加入stm32f7-disco移植；
* 在stm32f10x中新加入CAN驱动及应用代码示例；
* 在stm32f40x中加入硬件定时器驱动，RTC驱动；
* 调整stm32f107为新的串口驱动框架；

## 组件

* DFS的struct stat定义中移除st_blksize成员（可以兼容于VC++中的stat定义）；
* 修正DFS中select实现的问题；
* 修正DFS中文件操作出错、关闭时的fd处理问题；
* 修正DFS中mkdir和lseek出错时的fd处理问题；
* 修正lwIP中SYS_ARCH_PROTECT/SYS_ARCH_UNPROTECT保护的问题；
* 增加CAN驱动框架；
* 增加硬件定时器驱动框架；
* SD/MMC驱动框架中增加eMMC支持；
* 修正注册SDIO驱动时驱动关联的问题；
* 修正串口驱动框架DMA发送时激活标志的问题；
* SPI Flash驱动中加入对GD25Q spi flash芯片支持；
* 增加paho-mqtt组件移植；
* 增加msh的脚本执行能力，可以在msh下执行*.sh脚本；
* 增加msh下的mkfs命令；
* 修正在Linux Telnet下使用finsh shell回车符处理的问题；
* 增加应用模块在使用armcc、gnu gcc编译器时的libc符号导出；
* 在以太网网卡驱动框架中增加ETHIF_LINK_AUTOUP/PHYUP参数用于指定初始时的链路Up/Down状态；
* 在组件初始化中导出log_trace组件；

## 内核

* 更改UNUSED/USED等更改成RT_UNUSED/RT_USED；
* 链接时增加.rodata.name section，当空间资源受限时可以把它放到性能低的内存区域；
* 完善IAR编译器下的组件自动初始化；
* 增加rt_assert_hook，在触发断言时可以执行这个钩子函数；
* 修正应用模块分散加载情况下的问题；

## 工具

* scons中定义Group时加入了本Group内的编译参数定义；
* 修正了如果Group中即包含代码，也包含二进制库时，生成的Keil MDK工程文件有两个重名Group的问题；

版本: RT-Threadv2.0.1及v2.1.0 alpha

RT-Thread v2.0.1是2.0这个系列的bug修正版，而v2.1.0 alpha则是当前开发主干的一个技术预览版本，它给出了v2.1.0这个版本系列的技术预览情况，不建议用于实际产品中，因为它可能存在大量的一些bug。

# RT-Thread v2.0.1更改说明

*  IAR用的dlib，加入THREAD_SUPPORT 和 FILE_DESCRIPTOR的支持；
*  修正finsh中echo回显模式的问题；
*  修正USB host代码的编译错误；
*  修正sensor框架回调函数的问题；
*  修正pin设备注册时的设备名称问题；
 
而v2.1.0 alpha这个技术预览版则沿着最初设定的roadmap技术路线进行，这其中主要包括：

*  lwip更深度的集成：把它集成到RT-Thread的文件系统接口中，这样Linux/Unix下的一些socket网络应用能够更顺利的移植到RT-Thread上，也为以后可以应用到更多地方的select接口铺路。

*  这部分是和RT-Thread发布本身无关，但也是这个版本系列设定的目标之一：开启一个云端集成开发环境的时代！云端会是什么样的，请用现代化的浏览器打开[CloudIDE](http://lab.rt-thread.org/cloudide/simulator/index.html)

# RT-Thread 2.0.0正式版更改说明

经历了大约1年的时间，RT-Thread v2.0.0的最终版本终于发布出来了。自这个版本开发以来，引入了多项功能、修改、增强等。感谢参与的诸位开发人员！
以下是自v2.0.0 RC版本以来的详细更改记录。后续我还会给出v2.0.0版本自v1.2.x版本的主要不同、看点，以及给出下一个版本的roadmap规划。

## 内核
 
*  console以RT_DEVICE_FLAG_STREAM参数打开字符设备；
*  在rt_memheap_free中加入更多的断言检查；

## 组件

*  更新RW009驱动以支持Wi-Fi SoftAP模式（aozima）；
*  修正sensor框架的一些问题，并加入C API接口（睿赛德服务公司提供）；
*  加入MPU6050 sensor的代码（bernard, Coing）；
*  加入BMI055 sensor的代码（Coing）；
*  当未使能heap时，修正finsh/msh中list_memheap的问题；
*  修正LIBC编译的警告；
*  加入IAR dlib相关的移植，使得应用能够使用标准的API接口；
*  修正YMode握手时可能引起的竞争问题（grissiom）；
*  更新FreeType版本到2.5.4
*  单独把C++的全局对象初始化放到cplusplus_system_init函数中，并在初始化线程中调用；
*  finsh中以RT_DEVICE_FLAG_STREAM参数打开字符设备；
*  添加VBUS组件用于Linux与RT-Thread系统之间，RT-Thread与RT-Thread系统之间通信（睿赛德服务公司捐赠）；
*  增加lwIP/NAT组件，可以做多个网口间的地址转换（Hicard）；
*  增加lwIP/DHCP服务端，用于向客户端分配IP地址（睿赛德服务公司提供）；
 
## BSP

*  修正LPC4357串口驱动初始化时过早打开中断的问题（nongxiaoming）；
*  重写LPC4357串口驱动，并让芯片上M4/M0核心分别都执行RT-Thread系统，两核心之间以VBUS组件进行系统间通信（睿赛德服务公司捐赠）；
*  新增RX移植（limxuzheng）；
*  新增NuMicro M051 Series移植，支持GCC、Keil MDK编译器（bright-pan）；
*  新增LPC54102移植（Coing）；
*  移除STM32F4 BSP中不需要的RT_TIMER_TICK_PER_SECOND配置（pangweishen）；
*  在Linux Clang编译分析中，强制以32位模式进行编译（grissiom）；
*  修正STM32F103中串口驱动中断过早打开的问题（armink）；

## 工具

*  增加scons中的MD5支持（bright-pan）；

# RT-Thread 2.0.0 RC 更改说明

发布时间:2014/11/4

随着RT-Thread功能越来越多，如何发布版本也成为一件头疼的事情，因为需要仔细对比最近三个月来的修改记录。这次的发布距离上一次beta版本依然是三个月的时间，但按照发布计划已然推迟了一个月进行发布。 

在这三个月中，开源社区上也发生了很多有趣的事情：

阿嘉的使用RT-Thread的四轴飞行器毕业设计惊艳亮相，采用了1个STM32F4 + 8个STM32F1进行飞行控制，总计9个MCU的另类实现方式；沿循四轴飞行器的路线，与国内匿名团队合作，采用RW009 Wi-Fi控制的迷你四轴飞行器也在稳步推进过程中。

RT-Thread做为一个开源组织参与的CSDN开源夏令营结出了丰硕的果实：
由hduffddybz参与的IPv6协议栈移植（最新版本的lwIP-head版本移植）在这次发布中已经包括进来，从而能够在使用RT-Thread的小型设备上实现TCP/IP v4/v6双栈的支持；
由wzyy2参与的GDB stub实现，也完美的支持BeagleBoneBlack开发板和STM32F4平台；
CSDN开源夏令营其他的成果，例如bluedroid移植也有了初步的成果，希望能够在后续的版本（可能会是2.1.0系列版本？）包含进来。CSDN开源夏令营是一次非常棒的活动，能够让学生提前进入实战，了解软件开发的初步知识。对开源社区来说，也是一次非常有益的社区互动活动。希望明年这个活动可以继续，关注RT-Thread、嵌入式开发的同学可以关注明年的动向。

当前智能化设备是一个备受关注的领域，针对这一领域的特点，RT-Thread也相应的做出了积极的响应，所以这个版本开始加入sensor的应用框架（APP/算法 <--> sensor framework <--> RT-Thread device driver <--> 硬件外设）。希望在小型化的RT-Thread操作系统基础上融合智能化相关的技术，让RT-Thread成为这方面可选的OS系统之一。RT-Thread操作系统的sensor框架也尝试新的实现方式，即采用C++的方式来实现（当然也会考虑C方面的兼容，无疑C++的面向对象特性会更好，所以最终选择了C++），在这个基础上也可能融合其他的一些生态技术，例如ARM mbed平台上的一些社区组件技术。所以这个发布版本中既包括sensor框架，也包括了C++底层的一些基础支撑。

这个版本是RT-Thread 2.0.0系列正式版本的候选版本，正式版本预计会在年底正式发布，距离正式版本还会加入更完善的一些支撑（例如各种传感器驱动）。也计划2014年11月22日，在上海浦东举行RT-Thread嵌入式系统沙龙活动，欢迎大家关注并参与进行RT-Thread方方面面的技术交流。

以下是这个版本的更改记录:

## 内核

* 修正当采用高级别优化编译时，idle任务中查询是否有僵尸线程的潜在bug；

* 修正memory pool中的竞争问题；

* 在console中打开设备时，加入流标志进行打开；

## 组件

* 加入C++基础支撑组件。C++组件依赖于RT_USING_LIBC库，当使用GCC编译器时请注意查看其中的说明文档并更改ld script；
* 修正DFS中NFS打开目录的bug；
* 更改DFS ROMFS默认romfs_root为弱化符号；
* 添加DFS中dfs_file_lseek接口中关于fs的检查；
* 移除I2C core中无用的core lock锁；
* 添加sensor framework（采用C++的方式支持各种sensor）；
* 修正serial框架中DMA发送的bug（heyuanjie87）；
* 移除SPI框架中不必要的device初始化代码；
* 完善SPI Wi-Fi网卡RW009驱动并提供RSSI相关的命令；
* 修正MSH中未定义DFS_USING_WORKDIR时更改当前目录的bug；
* 修正MSH中未定义RT_LWIP_TCP时依然定义了netstat命令的bug；
* 修正MSH中未定义RT_USING_HEAP时依然定义了free命令的bug；
* 修正finsh中FINSH_USING_HISTORY相关的裁剪；
* 加入gdb stub组件，当前支持ARM Cortex-A8和Cortex-M3/4（wzyy2）；
* 统一不同编译器下使用LIBC的宏为RT_USING_LIBC，原有的宏定义RT_USING_NEWLIB/RT_USING_ARM_LIBC需要从rtconfig.h中移除，并替换成RT_USING_LIBC；
* 加入最新的lwIP分支：lwip-head，以提供IPv4/v6双栈的功能（hduffddybz）；
* YMode中打开串口设备时，添加open flag（armink）；

## bsp

* 加入北京京微雅格的M7（华山）低功耗FPGA的ARM Cortex-M3移植（aozima）；
* 加入北京京微雅格的M7 EMAC以太网驱动（aozima）；
* AT91SAM9260分支中更改RT_USING_NEWLIB为RT_USING_LIBC；
* BeagleBoneBlack分支中加入gdb stub支持（wzyy2）；
* LPC176x分支中加入C++支持；
* LPC176x分支中修正SD卡驱动返回卡信息的bug；
* 修正LPC408x分支中GCC编译时的问题；
* LPC408x分支中加入C++支持；
* 龙芯1B分支中加入UART3驱动；
* 加入飞索半导体的MB9BF568 FM4分支移植（yangfasheng）；
* mini2440分支中更改RT_USING_NEWLIB为 RT_USING_LIBC；
* stm32f0x分支中移除不同编译器下的LIBC定义，统一更改为RT_USING_LIBC；
* stm32f0x分支中加入串口接收溢出中断处理（armink）；
* stm32f40x分支中加入gdb stub支持并添加UART6驱动（wzzy2）；
* zynq7000分支中更改RT_USING_NEWLIB为RT_USING_LIBC；
* 加入ARM Cortex-M4芯片指令级的ffs实现；
* 修正MB0BF618S分支中缺少timer初始化的bug（mike mao）；

## 工具

* 移除Python 2.6中未支持的语法（xfguo）；
* 移除Windows平台中的startupinfo信息（对Python版本兼容性更好）；
* 修正CPPPATH被打乱的bug；

# RT-Thread 2.0.0 Beta更改说明

发布时间:2014/8/1

v2.0.0这个版本系列是RT-Thread当前的开发分支，如果要上新项目，建议使用这个版本来进行，预计这个版本的正式版会在年底发布。欢迎对这个版本进行测试、并反馈问题，能够早日进入到稳定版。

v2.0.0版本的开发相对活跃些，开源社区提供了强有力的支持：如Arda贡献的TM4C129x移植，Romeo贡献的frdm-k64f移植，xiaonong的LPC4300移植等，以及睿赛德服务公司捐赠的Zynq7000移植，MB9BF618S移植，以及SPI WiFi网卡的驱动代码等。

更改记录

## 内核

* 移除rt_device_init_all()函数：在系统启动时不需要再调用这个函数来初始化驱动，而是由上层应用执行rt_device_open时自动进行设备初始化；
* 修正设备对象引用计数在打开设备失败依然递增的问题；
* 增加WEAK宏用于定义/声明弱符号；
* 在执行静态内存块分配前，重置线程的errno；
* 修正timer未打开调试选项时，无用的静态函数定义（导致编译警告）；
* 启动timer前，对timer进行强制移除；
* 在执行soft timer超时函数时，打开调度器锁；
* 新增块设备的自动刷新参数，RT_DEVICE_CTRL_BLK_AUTOREFRESH；
 
## 工具

* 修正scons命令编译时，选择keil mdk (armcc)编译器时，命令行太长编译失败的问题；

## 移植

* 移除rt_device_init_all()相关的调用；
* 根据串口框架调整相关的驱动代码；
* 新增frdm-k64f移植（FreeScale K64芯片）；
* 移除K60Fxxxx移植；
* 新增LPC43xx移植（NXP LPC4357芯片）；
* 移除LPC176x中的组件初始化配置；
* 修正龙芯1B移植（ls1bdev）中链接脚本关于组件初始化部分的配置；
* 修正STM32F40x中UART3的配置；
* 修正STM32F40x中GNU GCC连接脚本中ROM/RAM大小的配置；
* 移除STM32F107中的组件初始化配置；
* 增强STM32F107 EMAC驱动性能，同时加入自动查找PHY芯片地址功能；
* 重写xplorer4330（NXP LPC4330芯片）移植（xiaonong完成）；
* 新增Zynq7000 ARM Dual Cortex-A9移植；
* 新增MB9BF618S移植；
* 新增tm4c129x移植，并加入相应的EMAC以太网驱动；

## 组件

* DFS: 新增根据设备对象获得其上装载文件系统路径的函数：dfs_filesystem_get_mounted_path(struct rt_device* device);
* DFS: 修正readdir在GNU GCC下的编译警告；
* DeviceDrivers：新增workqueue实现；
* DeviceDrivers: 修正USB Device栈中的一些拼写错误；
* DeviceDrivers: 重写serial框架，能够让串口设备驱动同时支持三种模式：poll、interrupt、DMA。模式选择需要在执行rt_device_open时，由open flags指定；
* DeviceDrivers: 加入更多的SPI设备驱动，例如RW009的SPI WiFi网口驱动（2.4G 802.11 b/g/n，WEP/WPA/WPA2，SoftAP/Station），SPI NorFlash块设备驱动，ENC28J60以太网网卡驱动；
* Finsh: list_device()命令中增加refcount的信息；
* Finsh: 修正'0'零常量无法识别的错误；
* Finsh: mv命令，实现把一个文件移动到一个目录中；
* Finsh: ifconfig命令支持对一个网络接口的基本配置；
* Finsh: 新增netstat命令，用于显示当前系统中TCP连接的状态；
* Finsh: 修正当命令行太长导致的缓冲区移除的问题；
* libc: 修正arm libc中未使用DFS时的编译警告；
* libc: 修正newlib中使用DFS时的系统调用编译警告（GNU GCC下）；
* lwIP 1.4.1: 默认打开LWIP_SO_SNDTIMEO以支持连接发送超时；
* lwIP 1.4.1: 修正MEMP_NUM_TCP_SEG定义错误的问题；
* lwIP 1.4.1: 加入RT_LWIP_REASSEMBLY_FRAG选项定义以支持IP分组及合并；
* lwIP 1.4.1: ethnet网络接口支持定义LWIP_NO_TX_THREAD/LWIP_NO_RX_THREAD，以关闭etx/erx线程；
* lwIP 1.4.1: 用户可以重新定义RT_LWIP_ETH_MTU，以修改网络中的MTU值；
* lwIP 1.4.1: 修正LWIP_NETIF_LINK_CALLBACK条件编译的问题；
* lwIP 1.4.1: 完善移植相关的注释；
* log trace: 增加log_session_lvl接口；
* log trace: log trace中的session引用更改成常量形式；
* ymodem: 增强数据接收的稳定性；

# RT-Thread 2.0.0 Alpha更改说明

发布时间:2014/4/8
	
RT-Thread 2.0.0分支的第一个技术预览版本，仅用于展示2.0.0发展分支的演化动向(按照roadmap，2.0.0这个分支会有一部分RT-Thread和Linux互补性的技术，为Linux增加更好的实时性，为RT-Thread增加更多的功能性，这份技术预览版正是朝着这个目标而努力)，欢迎反馈建议和问题。

## 组件

* msh： bugfix 和功能性增强。新的 msh 在调用外部模块方面更加方便。
* DFS： nfs 的 bugfix 和内置命令的增强。ELM FatFS加入对扇区不匹配情况下的信息输出，这样能够及时定位问题。
* JS：新添了轻量级Javascript引擎，可以在RT-Thread中直接运行javascript脚本。
* VMM：可以在qemu中运行的 Virtual Machine Module 组件。暂时只支持 realview-pb-a8 的 bsp。
* CMSIS：版本更新至 3.20
* drivers：USB 协议栈的重构。新的框架中编写驱动变得更加容易了。

## BSP

* beaglebone：串口驱动更新
* realview-a8：添加了 VMM 组件

## 工具

* 固件加入scons --target=ua -s，用于准备用户应用环境；

[发布后记]

RT-Thread 2.0.0. Alpha版本相比于RT-Thread 1.2.1，新的特性主要有两部分：
- RT-Thread + Linux双系统，这部分以RealView-A8处理器(ARM Cortex-A8单核)为蓝本，给出一个简单的双系统并行运行的demo；在没有硬件的环境下，可以使用QEMU软件虚拟方式的执行。这个链接中包含一个编译好的Linux及RT-Thread二进制包，可以直接下载进行体验。

目录中有 Linux 的内核镜像 zImage，ramdisk rootfs.cpio.gz。可以用
qemu-system-arm -M realview-pb-a8 -kernel zImage -initrd rootfs.cpio.gz -serial vc -serial vc
来启动。启动之后 Linux 的控制台在第一个串口上(Atl + Ctrl + 3)，可以直接无密码以 root 用户登录。登录之后加载内核模块：
insmod rtvmm.ko
来启动 RT-Thread。RT-Thread 启动之后控制台在第二个串口上(Atl + Ctrl + 4)。第一个串口Linux shell依然可以使用，第二个串口则是RT-Thread的shell。
- JavaScript解析器，这个是由牛头哥移植的，可以在一个非常小资料的MCU上以JavaScript脚本方式进行编程、开发。根据这种方式，也提供了RN001JS的以太网硬件模块：以JavaScript脚本语言作为二次开发，提供在线web(即WebIDE)进行编程并运行JavaScript程序。JavaScript作为一门轻量级、解释型的语言，更容易上手，配合WebIDE、及提供的一些example可以使得开发变得非常的轻松，也包括一些传感器的JavaScript例子，让做网页的人也可以玩硬件了！

# RT-Thread 1.2.1更改说明

发布时间: 2014/4/8
	
在原有的1.2.0版本的bug修正版本，也是1.2.0系列的第一个修正版本，原则上不添加任何的新功能，我们尽量会按照每个季度一个修订版本的方式推进。大家在使用的过程中有什么问题还请反馈给我们，这些问题很可能会在下个版本中修正！

以下是更改记录：

## 内核

* 用户应用，增加用户应用命令行参数支持；
* 在挂起一个任务时，把相应的定时器也关闭；

## BSP

* BeagleBone，加入更多串口驱动支持；
* 移除BSP中rt_device_init_all函数调用，改成打开设备时自动进行初始化；
* LPC176x，移除components初始化管理器；
* LPC4088，修正LED驱动的问题；
* STM32F107，移除components初始化管理器；

## 组件

* 文件系统，ELM FatFS加入对扇区不匹配情况下的信息输出，这样能够及时定位问题；
* 文件系统，NFS网络文件系统修正相关的一些编译警告信息；
* 文件系统，copy命令加入文件夹方式复制功能；
* 文件系统，RAMFS，加入到components初始化管理器中；
* 文件系统，ROMFS，用于转换文件的工具mkromfs.py，增加Linux主机的支持；
* CMSIS更新到3.2.0版本；
* 串口驱动框架加入serial->ops->control的调用；
* 命令行系统，优化msh，支持用户应用的命令行参数；
* 命令行系统，当使用msh时，默认使用msh >的命令行提示符；
* TCP/IP协议栈，导出更多的lwIP接口给用户应用；
* POSIX thread，修正了同时使用lwIP组件时的编译警告；
* 第三方组件，加入TJPGD的移植，加入libpng的移植；

## 工具

* 固件加入scons --target=ua -s，用于准备用户应用环境；

[发布后记]
* RT-Thread携带了众多的BSP，不一定能够一一保证每个分支上把RT-Thread上相应的功能使用起来。所以针对这种情况，我们有一款评估用的硬件开发板：RealBoard 4088，在上面力求把一些相关例程都添加上，这样在一个基本的BSP基础上，可以对照着把其他的组件、功能添加进去；
* RealBoard 4088使用的RT-Thread版本主要以RT-Thread 1.2.1版本为主。

# RT-Thread 1.2.0正式版本更改说明

发布时间: 2014/1/6 

实现roadmap中提到的大部分内容
	
1，文档方面已完成《RT-Thread编程手册》，同时还有论坛上jiezhi童鞋的《一起来学RT-Thread系列连载教程》
2，BSP分支方面新增cortext-A8(beaglebone)，cortext-R4(rm48x50)，UNITY-2(SEP6200),lpc408x的移植
3，组件方面：
- 加入msh(类似linux shell的风格)，能够直接执行应用程序
- 新增freemodbus 1.6.0的移植
- 新增开源的嵌入式关系数据库SQLite 3.8.1的移植
- 新增Ymodem协议
- 默认使用lwIP 1.4.1

下面是自RT-Thread 1.2.0 RC版本发布以来具体的变更履历：

## 内核

* timer.c - 使用跳跃表(skip list)实现系统定时器链表，并在bsp中的startup.c中重新加入定时器初始化函数rt_system_timer_init()
* rtdebug.h - 新增宏定义RT_DEBUG_IN_THREAD_CONTEXT
* idle.c - 在函数rt_thread_idle_excute()中一次清除所有的死线程
* scheduler.c - 新增API rt_critical_level()返回调度器上锁次数

## 移植

* cortex-m0 - 修正 cortex-m0 GCC移植中hardfault的问题点
* cortex-r4 - 在startup后释放IRQ堆栈空间
* cortex-r4 - 按字节长度分配堆栈空间

## BSP分支

* 新增lpc408x移植
* bsp/stm32f0x - 增加USART1，USART2驱动，支持finsh，支持组件初始化
* bsp/simulator - 当RTGUI配置无效时打印错误信息
* bsp/simulator - 默认情况下关闭RTGUI选项
* bsp/simulator - 增加createdef.py文件来生成VS的def文件
* bsp/simulator - 当使用VC++编译时去除_TIME_T_DEFINED的定义
* bsp/xplorer4330 - 重命名文件Retarget.c为retarget.c,否则linux系统中编译会报错
* bsp/xplorer4330 - 修正GCC编译链接时关于ENTRY的警告
* bsp/rm48x50 - 新增GCC的移植
* bsp/K60Fxxxx - 修正一个编译错误

## 组件

* dfs - 正确处理mkfs未实现的情况
* dfs - 使用指针代替index变量
* dfs - 在函数dfs_filesystem_lookup()将含义模糊的指针变量名称empty重命名为fs
* dfs - 修正dfs_unmount问题点
* dfs - 在设备打开错误时令挂载失败
* dfs/elmfat - 令elmfatfs每次都检查扇区大小
* net - 新增freemodbus 1.6.0的移植
* finsh - 新增FINSH_USING_MSH_ONLY选项
* finsh - 只有当shell设备为空时调用rt_console_get_device()
* finsh - 修正FINSH_USING_SYMTAB未定义的错误
* finsh - 重构control按键的处理
* msh - 增加文件和路径名称自动补全的功能
* msh - msh内增加执行module的功能
* msh - msh内增加更多的命令
* libc - 修正 _sys_read()/_sys_write()问题点
* external - 增加开源的嵌入式关系数据库SQLite 3.8.1的移植
* pthreads - 避免ESHUTDOWN重复定义
* mtd_nand - 在MTD nand中增加更多的调试措施
* mtd_nand - 修正操作MTD nand时起始块错误的问题
* lwip-1.4.1 - 在lwIP内加入更多的RT-Thread选项设置
* log_trace - 修正函数memmove()参数使用错误的问题
* drivers/pipe - 增加一个control命令来获得pipe剩余的空间
* drivers/serial - 如果读写长度为0，则立即返回

## 例程

* examples - 用rt_sem_control()中的RT_IPC_CMD_RESET命令rt_sem_trytake()来清除信号量
* examples - 始终打印输出测试结果
* examples - 在所有的测试结束后打印输出简报
* examples - 在TC线程中清除变量_tc_stat的TC_STAT_RUNNING状态
* examples - 重新实现loop功能，并新增finsh命令tc_loop
* examples - 在tc_stop中增加延时，由原来的延时RT_TICK_PER_SECOND/2调整为10 * RT_TICK_PER_SECOND
* examples - 在SConscript中判断TC如果被使能，在CPPPATH中增加TC路径
* examples - 新增一个in-mem-log的例子
* semaphore_priority.c - 在cleanup时释放信号量
* heap_realloc.c - 检查调用realloc(ptr, 0)是否成功
* thread_delete.c - tc线程的延时应该比tid2的延时长，保证其测试过程中正常运行
* thread_delay.c - 放宽超时判断条件，因为当RT_TICK_PER_SECOND为1000时，容易产生1个tick的误差
* semaphore_static.c - 放宽超时判断条件，因为当RT_TICK_PER_SECOND为1000时，容易产生1个tick的误差
* semaphore_dynamic.c - 放宽超时判断条件，因为当RT_TICK_PER_SECOND为1000时，容易产生1个tick的误差

其他：
* 更新README.md
	
# RT-Thread 1.2.0RC更改说明

发布时间: 2013/10/10/ 10:19
	 
主要说明: 该版本新增ARM Cortex-A8的支持(BeagleBone)，新增UNITY-2内核的支持(SEP6200)，新增Ymodem协议。

变更履历
========

[内核]

* 修正rtdef.h中的拼写错误(_MSC_VER_ -> _MSC_VER)
* 修正scheduler.c中的调试打印输出错误
* ipc - 在函数rt_event_recv()中增加对参数option有效性的检查
* device - 增加统计设备引用次数的变量ref_count
* memheap - 修正内存块分割问题点
* memheap - 优化函数rt_memheap_realloc()
* kservice - 函数声明使用rt_vsnprintf代替vsnprintf


[组件]

* dfs - 修正dfs_file.c中一处变量参数类型错误的问题
* dfs - 增加mount table
* dfs - 在building脚本中加入ramfs的支持
* dfs - 修正ramfs中O_APPEND write的问题
* dfs/elm - 在mkfs中加入device_open/close
* dfs/jffs2 - 修正jffs2_opn/opendir中的f_flag初始化问题
* dfs/jffs2 - 修正jffs2卸载问题
* pthread - 修正一处编译警告
* drivers/pipe - 增加rt_pipe_init/rt_pipe_detach
* drivers/pipe - 增加非阻塞读写和强制写模式
* drivers/pipe - 当恢复读的时候调用函数rx_indicate()
* drivers/pipe - 增加一个设备类型(pipe类型)
* drivers/portal - 实现portal设备类型
* drivers/ringbuffer - 修改一些模糊不清的函数名称
* drivers/ringbuffer - 新增put_force和putchar_force接口函数
* finsh - 当set_device时增加设备检查
* finsh - 在rx_ind中增加对shell设备的自动设置
* finsh - 增加pipe和portal设备的描述
* finsh - 在变量定义时使用别名
* finsh - 当关闭设备时注销rx_indicate
* finsh - 修正命令行太长的问题
* finsh/msh - 只有当DFS_USING_WORKDIR使能时才声明cd/pwd
* init - 为新的组件初始化机制更新连接脚本
* init - 增加组件初始化调试代码
* logtrace - 整理代码，去除编译警告
* logtrace - 增加LOG_TRACE_VERBOSE
* logtrace - 调整log values
* logtrace - 只有当finsh使能的时候才声明cmd
* libc/minilibc - 在sys/time.h中增加gettimeofday的声明
* utilities - 新增ymodem

工具:

* building.py - 增加clang静态缝隙器的支持
* building.py - 为Keil MDK增加buildlib功能
* building.py - 在clang-analyze中执行'clang -Wall -fsyntas-only'
* clang-analyze.py - 增加一个定制工具实现clang静态分析

分支:

* 新增BeagleBone的移植
* 新增SEP6200的移植
* 新增K60Fxxxx的移植
* 修正Linux中的编译错误(lm4f232, stm32f40x, xplorer4330)
* cortex-m3 - 加强hard fault的异常处理函数
* at91sam9260 - 更新串口驱动，使用组件中的通用串口驱动
* at91sam9260 - 更新工程目录结构
* at91sam9260 - 修正编译错误
* at91sam9260 - 内嵌GPLv2许可
* stm32f10x - 删除无用的文件
* stm32f10x - 更新工程目录结构
* stm32f10x - 更新工程文件
* stm32f10x - 为使用新的组件初始化更新连接脚本
* stm32f10x - 为使用新的组件初始化更新SD card驱动
* stm32f10x - 为使用新的组件初始化更新DM9000驱动
* stm32f10x - 更新串口驱动，使用组件中的通用串口驱动
* stm32f10x - 修正rtgui初始化问题
* simulator - 为使用新的组件初始化更新代码，以便支持mingw
* simulator - 支持Linux系统
* simulator - 修正Linux系统中的SDL初始化问题
* simulator - 在rt_components_init之后初始化SDL
* simulator - 将对SDL设置的内容移入drivers/SConstruct
* simulator - 在env中获得CORSS_TOOL和EXEC_PATH的值
* simulator - 支持clang-analyze
* simulator - 增加tap netif driver

//----------------------------------------------------------------------------------------

//----------------------------------------------------------------------------------------

//----------------------------------------------------------------------------------------


版本: RT-Thread 1.2.0 Beta 版本

发布时间: 2013/6/30
		
进过开发人员三个月的努力，RT-Thread 1.2.0 Beta 版本如期发布。
该版本默认采用lwIP 1.4.1协议栈，USB device stack也进一步完善。加入 log_trace 子系统，加入组件初始化升级版本，加入 ARM Cortex-R 的移植。

主要变化：

* 1，新增组件初始化功能
- 详情请看论坛帖子[新功能] 组件初始化
* 2，支持ARM Cortex-R系列处理器
- Grissiom 完成 ARM Cortex-R 的移植，目前BSP中已有TI RM48x50分支（仅支持TI CCS开发环境）
* 3，文件系统中新增 RAMFS
* 4，加入 log_trace 子系统
* 5，优化Cortex-M4线程上下文切换，使用了浮点运算的线程才保存及恢复FPU寄存器
- 详情请看论坛帖子[优化]cortex-m4f线程切换，优化FPU寄存器
* 6，新增API rt_memheap_realloc()
* 7，重新实现ringbuffer，采用镜像的方法区分“满”和“空”，同时支持任意大小的buffer
* 8，内核中加入RT_KERNEL_MALLOC/RT_KERNEL_FREE/RT_KERNEL_REALLOC宏。
如果用户未定义这些宏，将默认指向rt_malloc/rt_free/rt_realloc。
同时内核仅局限于使用这些宏来使用动态内存
* 9，在 building.py 中新增生成 cscope database 的选项
* 10，USB组件新增reset函数，支持热插拔
* 11，scons编译系统支持CCS开发环境
* 12，USB组件新增状态信息（USB_STATE_NOTATTACHED，USB_STATE_ATTACHED，USB_STATE_POWERED...）

修复问题点：

* 1，USB组件HOST可以挂起endpoints
* 2，simulator分支，修复 serial_write 问题
* 3，udisk可以被弹出
* 4，iar.py中修复绝对路径的问题
* 5，dfs_fs.h内增加dfs_mkfs()函数的申明
* 6，生成MDK工程文件的时候加入library文件
* 7，当PC不再接受数据的时候，重置VCOM相应的状态
* 8，USB组件：返回正确的LangID字符串长度给HOST
* 9，Cortex-M0，Cortex-M3，Cortex-M4上下文切换时，回收系统初始化时用到的栈空间

//----------------------------------------------------------------------------------------

//----------------------------------------------------------------------------------------

//----------------------------------------------------------------------------------------



版本: RT-Thread 1.2.0 Alpha版本

发布时间: 2013/4/10
	
遵循2013年RT-Thread roadmap，RT-Thread 1.2.0 Alpha版本发布，Alpha意味着此版本为技术预览版，仅用于展示RT-Thread 1.2.0未来的发展方向，并不适合于开发正式产品。RT-Thread 1.2.0版本是1.1.x系列的下一个分支，这个分支主要体现的是RT-Thread 1.x系列的文档情况。当然也有一些功能、代码方面的增强。

伴随着新版本的到来，RT-Thread有几个重大的转变：
1，代码托管从google code(SVN)迁移到github(GIT)
2，RT-Thread与RTGUI区分开来，并成为两个独立的开发分支
3，重视文档，将文档建设作为1.2.0版本的首要任务来抓

内核主要变化：
1，加入__rt_ffs函数用于实现32位整数中获取第一个置1的位；同时调度器中位图相关算法直接使用__rt_ffs函数；CPU移植时，可定义RT_USING_CPU_FFS，使用芯片指令完成。

2，新的中断注册机制
weety加入interrupt description功能，用于为interrupt增加更多的信息，同时中断服务例程也可以携带用户自定义的参数类型。
* 这部分对ARM7、ARM9、MIPS等影响很大，需要对CPU移植做相应的一些修改。
* 这部分对ARM Cortex-M系列芯片没有影响。

3，调整定时器插入位置，为相同超时定时的后面。

组件主要变化：
1，添加lwIP 1.4.1。
2，在finsh shell中加入module shell功能。finsh shell本身是一个C语言表达式的shell命令行，而module shell更类似于一个传统的命令行，由命令，参数等方式构成。

分支主要变化：
1，完善simulator分支，支持RTGUI，支持应用模块。
2，完善at91sam9260分支的移植及驱动更新。

编译系统主要变化：
1，开启省略编译时长命令特性，如果需要查看编译时命令行，可以使用scons --verbose查看。
2，加入生成CodeBlocks工程特性。
3，修正当系统安装使用Keil MDK 4.6+版本的问题。

github主要提交履历:
5646189b29: elm fatfs支持mkfs，并且无需提前执行dfs_mount; mount/umount/mkfs操作也不会引起reset
22786f8817: 允许用户自定义PID和VID
0001344105: 更明确的定时器运行机制，如果两个定时器在同一个时刻发生超时，那么先开始的定时器先处理
5d68ef8ec1: 修正使用64位GCC时编译finsh过程中发生错误的问题
a4d661dcf1: 修正dfs_elm.c中一处内存泄露，并且在mount fatfs失败时执行 umount fatfs操作
43228aeb9c: 修正list_tcps问题：ipaddr_ntoa不是可重入的函数。
3de4b92a68: 修正AT91SAM9260分支中PHY link状态错误的问题。
1abaa0492d

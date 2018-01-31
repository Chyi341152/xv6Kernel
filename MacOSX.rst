Mac OS X 操作系统详解：
    Fireware:
        Boot ROM Version: 用于扩展固件接口（Extensible Firmware Interface, EFI）,负责列出硬件设备管理和系统启动。
        SMC Version (System): 称为系统管理控制器(System Management Controller)固件，负责管理硬件的供电和散热。

    准备系统驱动器：
        通过GUID分区表（GUID Partition Table, GPT）进行分区的驱动器上，并且其中至少包含一个格式为Mac OS X 扩展（日志式）的卷宗。

    安装Mac OS X：
        安装过程先在目标驱动器上创建“恢复系统”完成后，Mac将重新启动到新创建的恢复系统（“Recovery HD”）Recovery HD 是一个隐藏的分区

    文件系统：
        GUID分区表（GUID Partition Table）这是基于Intel架构的Mac 默认使用的分区表，也是唯一能够支持基于Intel架构的Mac通过此磁盘存储设备进行启动的分区方案。
        Apple分区表（Apple Partition Map,APM）这是以前基于PowerPC架构的Mac 默认使用的分区表，也是唯一能够支持基于PowerPC架构的Mac进行启动的分区方案。所有基于Intel架构都可以访问该分区。
        主引导记录（Master Boot Record,MBR）大多数非Mac计算机都默认使用该类分区图方案，但是Mac无法通过该类分区启动，但是Mac可以访问MBR分区。
        
        卷宗格式：
            Mac OS 标准（Mac OS Standard）: 这是classic Mac OS 所使用的旧卷宗格式，是Mac OS 扩展卷宗格式的前身。不能作为Lion的启动卷宗
            Mac OS 扩展（Mac OS Extended）: 是Mac OS Standard 格式的升级，支持高级特性：包括Unicode文件名，丰富的元数据，POSIX权限，访问控制列表框ACL,
            Mac OS 扩展，大小写敏感（Mac OS Extended, Case-Sensitive）文件系统增加区分大小写的能力。
            Mac OS 扩展，日志式（Mac OS Extended, Journaled） Mac OS 扩展，大小写敏感，日志式（Mac OS X Extended, Case-Sensitive, Journaled）默认卷宗
            Mac OS 扩展，日志式，加密（Mac OS Extended, Journaled, Encrypted）Mac OS X 扩展，大小敏感，日志式，加密提供全盘的XTS-AES 128加密，也就是FileValue 2全盘加密保护所使用的技术。
            文件配置表（File Allocation Table, FAT）是Windows PC 和很多外设使用的旧卷宗格式
            扩展文件配置表（Extended File Allocation Table） ExFAT:专门为大容量的闪存存储驱动器所创建，支持32GB以上容量
            UNIX文件系统（UFS）UFS 是UNIX系统自身支持使用的原生卷宗格式，作为UNIX系统默认文件格式存在，
            NT文件系统（NTFS）Windows 7, 支持只读
            ISO 9600，光盘文件系统（Compact Disk File System, CDFS）只读CD媒体的通用标准
            通用光盘（Universal Disk Format, UDF）这是只读DVD媒体的通用标准

        软件RAID
            磁盘阵列（Redundant Array of Independent Disks, RAID）就是将相似的磁盘驱动器组合在一起使用可提升性能或可靠性大容量卷宗。

        终端管理权限
            
    数据管理：
        
    应用程序和进程：
        进程性能：
            抢占式多任务：避免单一进程长时间占用资源
            对称式多处理：使用多有可用的计算机资源，提供最佳性能，
        内存管理：
            保护式内存： 
            动态内存分配：
        进程安全：
            
    系统启动：
        Firmware (固件)Mac硬件检测并初始化，然后加载运行Booter引导程序。然后会有一声启动声
            BootROM: 位于Mac主板上闪存芯片
            Intel核心的Mac 固件基于Extension Firmware Interface (EFI)技术，
            Power-On Self-Test(开机自检)POST


        Booter(引导程序)将系统核心及必要的硬件驱动（核心扩展KEXT）加载入主要内粗，然后Kernel掌管整个系统，Booter会出现灰色苹果标志
        Kernel(核心)题哦那个基础功能，加载更多驱动，以及BSD UNIX系统内核，标志是苹果标志下面出现循转的灰色齿轮
        系统Launche:加载操作系统内核后就开始第一个非核心的进程，系统级别的Launch,主要任务是加载系统的其他部分。
        
        苹果启动快捷键：
            Option: 启动到启动管理器中
            C:启动CD或DVD光盘
            D: 从Intel核心的Mac所配戴的第一张DVD光盘Apple Hardware Test分区中启动
            Command + Option + D: 通过网络连接到苹果服务器上，启动Apple Hardware Test 
            N : 从NetBoot 服务器启动
            Option + N: 
            Command + R:强制从恢复分区启动
            Command + Option + R:强制从Interner Recovery 
            Shift: 启动到安全模式
            Command + V : 详细模式 Verbose Mode 
            Command + S: 单用户模式 Sigle-user mode 
            Command + Option + P + R: 重置NVRAM设置，并重新启动


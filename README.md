# 关于关系型数据库系统的调研
##  什么是关系型数据库
关系型数据库以行和列的形式存储数据，以便于用户理解。这一系列的行和列被称为表，一组表组成了

数据库。用户用查询来检索数据库中的数据。所谓关系型数据库，是指采用了关系模型来组织数据的数

据库。关系模型指的就是二维表格模型，而一个关系型数据库就是由二维表及其之间的联系组成的一个

数据组织。
## 关于各类关系型数据库系统的简述
思路：各关系型数据库既有优点也有缺点，其优点决定了其特殊的适用场景，缺点也限制了它的使用场

合。
### SQL Server
- 说明

Microsoft SQL Server是微软公司开发的大型关系型数据库系统。微软同Sybase 签订了合作协议，使

用Sybase的技术开发基于OS/2平台的关系型数据库。1989年，微软发布了SQL Server 1.0 版。 

Microsoft在与Sybase分道扬镳后，随后在其6.05和7.0版本中重写了核心数据库系统。
- 优缺点及适用场景

  - SQL Server的功能比较全面，效率高，操作简单，管理方便，维护和管理费用较低，因此可以作为中

型企业或单位的数据库平台。
SQL Server可以与Windows操作系统紧密集成，不论是应用程序开发速度还是系统事务处理运行速度，

都能得到较大的提升。因此，对于在Windows平台上开发的各种企业级信息管理系统来说，不论是C/S（

客户机/服务器）架构还是B/S（浏览器/服务器）架构，SQL Server都是一个很好的选择。
 - SQL Server的缺点是只能在Windows系统下运行，没有丝毫的开放性，而且windows平台的可靠性，安全

性和伸缩性是非常有限的。因此Windows9X系列产品是偏重于桌面应用，NT server则适合各种大中小型

型企业。 

### Sybase
-说明 
美国Sybase公司研制的一种关系型数据库系统，是一种典型的UNIX或WindowsNT平台上客户机/服

务器环境下的大型数据库系统。Sybase通常与SybaseSQLAnywhere用于客户机/服务器环境，前者作为服

务器数据库，后者为客户机数据库，采用该公司研制的PowerBuilder为开发工具，在我国大中型系统中

具有广泛的应用。

- 优缺点和适用场景
Sybase提供了一套应用程序编程接口和库，可以与非Sybase数据源及服务器集成，

允许在多个数据库之间复制数据，因此适于创建多层应用。
 
开发时间较长，升级较复杂，稳定性较好，数据安全有保障，支持优化查询。风险小。能在所有主流平

台上运行，C/S结构，可以用ODBC、Jconnect、Ct-library等网络客户连接。因此，在安全要求极高的

银行， 证券行业中得到了广泛的应用。 
SYBASE的价格是比较低的，但是SYBASE的在企业和政府中的应用较少，很难找到经验丰富的管理员，运

行管理费用较高。


###IBM 的DB2
- 说明
DB2是IBM著名的关系型数据库产品，DB2系统在企业级的应用中十分广泛。最近推出的DB2 Universal 

Database 6.1则是通用数据库的典范，是第一个具备网上功能的多媒体关系数据库管理系统，支持包括

Linux在内的一系列平台。
- 优缺点和使用场景
 - DB2具有很好的并行性，且操作简单。适用于数据仓库和在线事物处理，性能较高，因此多用于客户

端支持及应用模式。
 
###Oracle
- 说明
Oracle 前身叫SDL，由Larry Ellison 和另两个编程人员在1977创办，他们开发了自己的拳头产品，在

市场上大量销售，1979 年，Oracle公司引入了第一个商用SQL 关系数据库管理系统。Oracle公司是最

早开发关系数据库的厂商之一，其产品支持最广泛的操作系统平台。目前Oracle关系数据库产品的市场

占有率名列前茅。
- 优缺点和使用场景
 - 能所有主流平台上运行（包括 windows）完全支持所有工业标准采用完全开放策略使客户选择适合

解决方案对开发商全力支持
Oracle 多层次网络计算支持多种工业标准用ODBC、JDBC、OCI等网络客户连接 
 - 对硬件的要求很高；
价格比较昂贵；
管理维护麻烦一些；较复杂, 同时提供GUI和命令行，在Windows NT和Unix， Linux 下操作相同。对数

据库管理人员要求较高。 

###mySQL
- 说明
mySQL是一个小型关系型数据库管理系统，开发者为瑞典MySQL AB公司。目前MySQL被广泛地应用在

Internet上的中小型网站中。
由于其体积小、速度快、总体拥有成本低，尤其是开放源码这一特点，许多中小型网站为了降低网站总

体拥有成本而选择了MySQL作为网站数据库。MySql有支持大型的数据库， 可以方便地支持上千万条记

录的数据库。作为一个开放源代码的数据库，可以针对不同的应用进行相应的修改。
- 优缺点及使用场景
 - MySQL拥有一个非常快速而且稳定的基于线程的内存分配系统，可以持续使用面不必担心其稳定性； 
MySQL同时提供高度多样性，能够提供很多不同的使用者介面，包括命令行客户端操作，网页浏览器，

以及各式各样的程序语言介面，例如C+，Perl，Java，PHP，以及Python。你可以使用事先包装好的客

户端，或者干脆自己写一个合适的应用程序。MySQL可用于Unix，Windows，以及OS/2等平台，因此它可

以用在个人电脑或者是服务器上。
 - MySQL最大的缺点是其安全系统，主要是复杂而非标准，另外只有到调用mysqladmin来重读用户权限

时才发生改变；
没有一种存储过程(Stored Procedure)语言，这是对习惯于企业级数据库的程序员的最大限制； 

# 恢复SQL Server

使用混合云备份服务（HBR）将SQL Server数据库备份到云上备份库后，您可以根据需要将备份的数据库恢复到源SQL Server、同备份库下其他SQL Server或者恢复至其他地域的SQL Server。

## 前提条件

已完成SQL Server备份。更多信息，请参见[备份SQL Server](/cn.zh-CN/ECS备份教程/ECS数据库备份/SQL Server备份/备份SQL Server.md)。

## 背景信息

恢复SQL Server数据库时，请注意以下事项：

-   恢复SQL Server数据库时若选择增量备份，将自动恢复全量备份。无需单独恢复全量备份后再恢复增量备份。
-   如需跨SQL Server恢复SQL Server数据库，请确保需要恢复的SQL Server版本低于或等于目标SQL Server版本。
-   恢复master数据库前，HBR会自动重启SQL Server并切换到单用户模式下运行。更多信息，请参见[还原master数据库](https://docs.microsoft.com/zh-cn/sql/relational-databases/backup-restore/restore-the-master-database-transact-sql?view=sql-server-2017)。

## 创建恢复任务

将备份的数据库恢复，具体操作如下：

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，选择**备份** \> **ECS数据库备份**。在ECS数据库备份页面，单击**SQL Server**。

3.  在页面上方，选择已备份数据库所在的区域。

4.  在数据库实例页签，找到目标SQL Server实例，在其右侧的操作列表，单击**恢复**。

5.  在新建恢复任务页面，按照配置向导，完成如下操作。单击**下一步**。

    1.  配置恢复内容。

        |参数|说明|
        |--|--|
        |恢复类型|数据库。|
        |可恢复数据库|从列表中选择待恢复数据库。|
        |恢复点类型|指定恢复点类型。        -   当您准备从指定时间点恢复时，选择**指定时刻**。
        -   当您准备从指定日志序列号恢复时，选择**指定LSN**。
        -   当您准备从指定备份文件恢复时，选择**指定备份**。在**备份集合**中，单击目标备份文件。 |

    2.  配置恢复计划。

        -   计划名称：本次计划恢复任务的名称。
        -   恢复时间：立即。表示立即恢复。
    3.  配置恢复选项。

        -   断线重连时间：恢复时，断开数据库后重新连接的时间间隔。
        -   速度限制：每秒恢复的数据大小。
    4.  配置恢复目标实例。

        选择恢复的目标数据库实例。默认为源SQL Server实例。

6.  单击**创建**。

7.  创建成功恢复任务后，系统开始恢复数据库。在**恢复任务**页签，可以看到您创建的恢复任务进度。

    ![restore](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8607091161/p232637.png)



# 恢复EMC Isilon

您可以将备份客户端中已备份的数据恢复到本地Isilon实例，或者将同仓库中的其他备份客户端的文件恢复到当前Isilon实例。

## 前提条件

已完成EMC Isilon备份。详情请参见[备份EMC Isilon](/cn.zh-CN/阿里云NAS备份教程/EMC Isilon备份/备份EMC Isilon.md)。

## 新建恢复任务

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，选择**备份** \> **NAS备份** \> **EMC Isilon**。

3.  在**Isilon实例**页签下，单击任意已完成的备份计划左侧的![+](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2303552061/p172225.jpg)图标。

    ![isilon](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8273073061/p176290.jpg)

4.  单击可用的历史备份点，选择**恢复**。

    您还可以选择**浏览**，查看要恢复的客户端下的所有文件。

    ![2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8273073061/p172253.jpg)

5.  在**恢复目的地**页签的恢复到Isilon区域，单击**选择已有Isilon**，选中然后单击**下一步**。

    您还可以添加Isilon实例，用于恢复备份客户端中已备份的数据。有关添加Isilon实例的详情，请参见[t1964189.md\#section\_ows\_gb4\_y3x](/cn.zh-CN/阿里云NAS备份教程/EMC Isilon备份/准备工作.md)。

6.  在**恢复客户端组**页签，单击**选择已有客户端组**，然后单击**下一步**。

7.  在恢复策略页签，填写**恢复路径**，选择**恢复规则**。

    恢复规则包含以下三项：

    -   **包含所有文件**：将恢复源客户端中的所有文件。
    -   **包含下列文件**或**排除下列文件**：您可以手动选中包含或者排除哪些文件，也可以手动输入要包含或排除的文件列表，然后HBR将按照规则恢复所选源客户端下指定的文件。
        -   手动选中文件

            您可以通过以下两种方式手动选中需要恢复的文件：

            -   展开Isilon实例下已备份的所有文件，选中您需要恢复的指定文件。
            -   在**搜索**框中输入文件名，并开启**高级**选项。

                此时，您可以按照业务场景需要，通过选择**搜索类型**、**最小数据量**、**最大数据量**以及文件的起始**修改时间**中的一项或者多项，从而快速查找想要恢复的文件。例如当您想要恢复的文件为test.txt，可直接在搜索框中输入test.txt，即可命中所有路径下包含的test.txt文件。

        -   手动输入文件列表

            文件列表每行填写一个路径，且每一行只能以源备份路径最后一个文件夹开头。

            -   恢复指定文件

                如备份路径为folder/test/data，要恢复data目录下的file.txt和abc.png，则文件列表填写如下：

                ```
                /data/file.txt
                /data/abc.png
                ```

            -   恢复指定目录

                如备份路径为folder/test/data，要恢复data目录下的所有文件或子目录，则文件列表填写如下：

                ```
                /data/
                ```

            -   恢复与通配符匹配的文件或目录

                如备份路径为folder/test/data，要恢复data目录下以abc为前缀的文件或子目录，则文件列表填写如下：

                ```
                /data/abc*
                ```

8.  单击**确定**。

    恢复任务创建后，您可以在恢复任务页签的**状态**栏查看恢复任务进度。



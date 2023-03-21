本实验延用[Azure Arc Enabled SQL Server](https://github.com/ZuoXuangn/SQLdemo/blob/main/Azure%20Arc%20Enabled%20SQL%20Server.md)中创建的 VM (Windows Server)进行测试。

实验中需要创建的 SQL Managed Instance 以及 subnet 均已配置

# 1.准备 SQL Managed Instance 环境

按照[Prepare your environment for a link - Azure SQL Managed Instance](https://learn.microsoft.com/zh-cn/azure/azure-sql/managed-instance/managed-instance-link-preparation?view=azuresql)配置SQL Server环境，配置完成之后，在SQL Server Configuration Manager ->SQL Server Services下面分别右击SQL Server 和 SQL Server Agent 进行重启。

![image](https://user-images.githubusercontent.com/34478391/226514357-87fe2732-37f8-4974-9670-3f0074b2497d.png)

在SQL MI 和 Windows VM 的 NSG中分别设置 Inbound Security Rules 和 Outbound Security Rules, 配置 5022 端口

![image](https://user-images.githubusercontent.com/34478391/226515349-31e46a58-42c0-4a91-89ce-68767d83384c.png)



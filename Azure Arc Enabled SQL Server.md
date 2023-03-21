本实验所需权限以及 resource provider 均已配置

# 1.创建window虚机#

参考[Quickstart: Create a Windows virtual machine in the Azure portal](https://learn.microsoft.com/zh-cn/azure/virtual-machines/windows/quick-create-portal),region 选择 "japaneast"，availability zone 选择"No infrastructure redundancy required",Image选择 "Windows Server 2022 Datacenter: Azure Edition - x64 Gen2"

![image](https://user-images.githubusercontent.com/34478391/226507704-66a5f75b-b793-4647-b4f4-e7a1ab119c55.png)

# 2.配置 Windows VM 进行测试

Azure Arc 不支持在Azure VM 上运行的SQL Server，但是可以参考 [Evaluate Azure Arc-enabled servers on an Azure virtual machine](https://learn.microsoft.com/zh-cn/azure/azure-arc/servers/plan-evaluate-on-azure-virtual-machine#reconfigure-azure-vm)对VM进行配置，用于本次实验测试

![image](https://user-images.githubusercontent.com/34478391/226508124-7f2d5c42-236b-4680-99d3-c9a47b8bfb6e.png)

# 3.创建 SQL Server-Azure Arc 并运行脚本

参考[Connect your SQL Server to Azure Arc](https://learn.microsoft.com/zh-cn/sql/sql-server/azure-arc/connect?view=sql-server-ver16&tabs=linux), license type 选择 "PAYG"

![image](https://user-images.githubusercontent.com/34478391/226508795-fbccc931-f8cc-4da9-b08b-7da0900b8f99.png)


![image](https://user-images.githubusercontent.com/34478391/226508846-8bd393bf-0230-4aae-8ad8-9bf9f45ae47e.png)

在 Window VM powershell上运行脚本 RegisterSqlServerArc.ps1，如果出现报错 ".ps1 is not digitally signed."：

![image](https://user-images.githubusercontent.com/34478391/226509131-bf212212-6d73-4077-bc9b-302d87209190.png)

请在 powershell中用Set-ExectionPolicy 设置执行策略：
```
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

再重新运行RegisterSqlServerArc.ps1

![image](https://user-images.githubusercontent.com/34478391/226509579-dddfbcc7-ccd3-4bca-8d7b-632ae9c1eb92.png)



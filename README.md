微軟試用版的系統叫做評估版，使用時間是180天。過期之後就會提示你需要激活。需要永久激活系統首先要轉為正式版。

總共兩個步驟，如果你還是不會轉，或者卡住在10%，那就建議你重新安裝正式版的吧。

1、管理員模式運行cmd,輸入命令:DISM /online /Get-CurrentEdition，得到結果：

C:\Users\Administrator>DISM /online /Get-CurrentEdition

部署映像服務和管理工具
版本: 10.0.20348.1

映像版本: 10.0.20348.202

當前版本為:

當前版本: ServerDatacenterEval

操作成功完成。

其中ServerDatacenterEval去掉Eval後，就是當前的Edition ID

2、輸入命令：DISM /online /Set-Edition:ServerDatacenter /ProductKey:WX4NM-KYWYW-QJJR4-XV3QB-6VM33 /AcceptEula 這裡的命令是升級Windows Server 2022 數據中心版的例子，如果是其他版本，需要替換掉對應的key和Edition，運行結果如下：

C:\Users\Administrator>DISM /online /Set-Edition:ServerDatacenter /ProductKey:WX4NM-KYWYW-QJJR4-XV3QB-6VM33 /AcceptEula

部署映像服務和管理工具
版本: 10.0.20348.1

映像版本: 10.0.20348.202

開始升級組件...
開始安裝產品密鑰...
產品密鑰安裝已完成。

正在添加程序包Microsoft-Windows-ServerDatacenterEdition~31bf3856ad364e35~amd64~~10.0.20348.169
[==========================100.0%==========================]
組件升級已完成。


重新啟動Windows 就變成正式版了。

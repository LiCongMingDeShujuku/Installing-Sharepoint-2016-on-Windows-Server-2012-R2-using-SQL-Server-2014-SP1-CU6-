![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 使用SQL Server 2014 SP1-CU6第1部分在Windows Server 2012 R2上安装Sharepoint 2016
#### Installing Sharepoint 2016 on Windows Server 2012 R2 using SQL Server 2014 SP1-CU6
**发布-日期: 2016年5月20日 (评论)**

## Contents

- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


How to install Sharepoint 2016 on Windows Server 2012 R2 using SQL Server 2014 SP1-CU6 (Part 1). Part 1 will show everything up to completing the prerequisites installation. Part 2 will pickup at the point of starting the actual Sharepoint 2016 installation. Just a quick note before we begin. If you are upgrading, and just following this along as a reference… Keep in mind that the upgrade path from any versions up to Sharepoint 2010 will need to run through Sharepoint 2013 then on up to Sharepoint 2016. The good news is; this could be a simple hop. You can get the 180 day demo for Sharepoint 2013, move your environment to it, then move it up to Sharepoint 2016 as a final destination. This is the recommended approach from Microsoft.
So lets get started. For starters; this tutorial will be carried out on Windows Server 2012 R2 Standard. Lets get the basics out of the way with a couple screenshots of the Server Environment. First; we are using Windows Server 2012 R2 Standard with SQL Server 2014 SP1-CU6
Windows Server 2012 R2 Standard

如何使用SQL Server 2014 SP1-CU6（第1部分）在Windows Server 2012 R2上安装Sharepoint 2016。第1部分里面有完成安装必备组件的所有内容。第2部分将在开始Sharepoint 2016实际安装时启动。在开始前我想简单说一下：

如果你正在升级，并希望从本文中获得参考…那么请注意，从任何版本到Sharepoint 2010的升级路径都需要通过Sharepoint 2013运行，然后再升级到Sharepoint 2016。好消息是，这个转换可以很简单。你可以获得180天的
Sharepoint 2013的试用，将你的环境移到它上面，然后将其移至最终目的地Sharepoint 2016上。 这是Microsoft推荐的方法。
我们开始。首先，本教程将在Windows Server 2012 R2 Standard上执行。让我们通过服务器环境的几个屏幕截图来了解一下基础知识。第一，我们使用的是Windows Server 2012 R2 Standard和SQL Server 2014 SP1-CU6。
Windows Server 2012 R2标准版

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-01.png?raw=true "#")
 
SQL Server 2014 SP1-CU6
SQL Server 2014 SP1-CU6

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-02.png?raw=true "#")
 
Also; here’s a quick screen-shot of the SQL Server Database Features which are installed in addition to the traditional Engine services and Management Tools.

下面是SQL Server数据库功能的快速屏幕截图，除了传统的引擎服务和管理工具之外，还安装了图里的这些功能。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-03.png?raw=true "#")
 
Next we’ll address the actual resources you’ll need to carry out the Sharepoint 2016 Installation.
Step 01:
Create two folders. These folders are will contain your Sharepoint 2016 Install file and the Sharepoint 2016 Prequisites. These are the 2 folders I’m creating under my E: Drive.
Folders:

E:1-SharePointServer2016
E:2-SharePointServer2016Prequisites ß Take note of this path. You’ll need it later.

Step 02: Download Sharepoint 2016:
https://www.microsoft.com/en-us/download/details.aspx?id=51493
Move this file to your 01-SharePointServer2016 Folder. Do NOT mount or install it yet.

Step 03: Download and Install the Windows Server 2012 R2 Update (KB2919355):
https://www.microsoft.com/en-us/download/details.aspx?id=42334
( This may have already been installed by your automatic updates (if you have that setup).

Remember to choose the correct update. Windows8.1-KB2919355-x64 It’s basically the largest file under the download. 690.8MB
Note: By installing KB2919355; you are automatically installing the other updates such as the following:
KB2919355, KB2932046, KB2937592, KB2938439, KB2934018, KB2959977

接下来，我们将介绍执行Sharepoint 2016安装所需的实际方法。
第一步：
创建两个文件夹。 这些文件夹将包含Sharepoint 2016安装文件和Sharepoint 2016 必备组件（Prequisites）。 这2个文件夹我建在E：Drive。
文件夹：
E：1-SharePointServer2016
E：2-SharePointServer2016Prequisitesß 注意此路径， 你一会会需要它。
第二步：下载Sharepoint 2016
https://www.microsoft.com/en-us/download/details.aspx?id=51493

将这个文件移动到你的01-SharePointServer2016文件夹。 先不要装载或安装它。
第三步：下载并安装Windows Server 2012 R2 升级版（KB2919355）：
https://www.microsoft.com/en-us/download/details.aspx?id=42334
你的自动升级（automatic updates）可能已经进行了自动安装（如果你设置了的话）。

请记住选对更新选项。Windows8.1-KB2919355-x64基本上是Download下的最大文件。690.8MB
注意：安装KB2919355了的话，你会自动安装其他更新，如下所示：
KB2919355，KB2932046，KB2937592，KB2938439，KB2934018，KB2959977

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-04.png?raw=true "#")

 
Once you have the file downloaded; just open it as you would with any .msu update installation. Right-Click, and select ‘Open with’.

文件下载之后，就像使用任何.msu更新安装一样，只需打开它，右键单击，然后选择“打开方式”。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-05.png?raw=true "#")
 
Select ‘Keep using Windows Update Standalone Installer’.

选择“继续使用Windows Update Standalone Installer”。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-06.png?raw=true "#")
 
Click ‘Open’.

点击‘Open’。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-07.png?raw=true "#")
 
Be patient as the installer completes.

耐心等待安装完成。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-08.png?raw=true "#")
 
Note: If you’re automatic update for the server is up to scratch; many of these updates will have already been installed including the appropriate .NET. Don’t be surprised if you see the following message:

注意：如果你的自动更新服务器是达标的，许多更新就已经安装好，包括适当的.NET。如果看到以下消息，请不要感到惊讶：

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-09.png?raw=true "#")
 
Step 04: Download the PreRequisites Powershell file Download-SP2016-RTM-Pre-requisites-Files.ps1:
https://gallery.technet.microsoft.com/office/PreRequisites-for-7f719ff3
Do not run the .ps1 file just yet at this point.

第四步：下载PreRequisites Powershel文件：Download-SP2016-RTM-Pre-requisites-Files.ps1
https://gallery.technet.microsoft.com/office/PreRequisites-for-7f719ff3
这时先不要运行.psl文件。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-10.png?raw=true "#")
 
Step 05: Download and install .NET 4.5.2 ( This may have already been installed by your automatic updates (if you have that setup).
https://www.microsoft.com/en-us/download/details.aspx?id=42642
Step 06:
Take note of the Sharepoint 2016 Product Key (Trial Version for 180 days): NQGJR-63HC8-XCRQH-MYVCH-3J3QR
Step 07:
Open Powershell on the server where you are installing Sharepoint 2016. Remember to ‘Run as Administrator’.

第五步：下载并安装.NET 4.5.2 这可能已经由你的自动更新安装好了（如果你有此设置）。
https://www.microsoft.com/en-us/download/details.aspx?id=42642
第六步：
注意这是Sharepoint 2016产品密钥（试用版180天）：NQGJR-63HC8-XCRQH-MYVCH-3J3QR
第七步：
在要安装Sharepoint 2016的服务器上打开Powershell。记住“以管理员身份运行”。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-11.png?raw=true "#")
 
You’ll need to set the execution policy to unrestricted/Remotesigned so you can install the prerequisites using the formerly downloaded Powershell file Download-SP2016-RTM-Pre-requisites-Files.ps1.
set-executionpolicy unrestricted -scope currentuser
Set-ExecutionPolicy RemoteSigned
Remember to agree to the prompt and type in ‘y’ for Yes, then press enter, and you’ll see the results below, and do the same for
你需要将执行策略设置为unrestricted / Remotesigned，以便使用前面下载的Powershell文件Download-SP2016-RTM-Pre-requisites-Files.ps1安装必备组件。
set-executionpolicy unrestricted -scope currentuser
Set-ExecutionPolicy RemoteSigned
记住同意提示并输入'y'表示是，然后按回车键，你会看到下面的结果，

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-12.png?raw=true "#")
 
Step 08:
Run the Powershell file you downloaded at Step 04 Download-SP2016-RTM-Pre-requisites-Files.ps1. Find the file, and right-click ‘Run as Administrator’.

第八步：
运行在第四步下载的Download-SP2016-RTM-Pre-requisites-Files.ps1 Powershell文件。找到该文件，然后右键单击“以管理员身份运行”。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-13.png?raw=true "#")
 
Click ‘Open’.
点击‘Open’。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-14.png?raw=true "#")
 
You’ll automatically be prompted for the folder name where you want to download the prerequisites files. You can get this from Step 01 above which in our case is: E:2-SharePointServer2016Prequisites 

系统将自动提示你输入要下载必备组件文件的文件夹名称。你可以从上面的第一步中找到，在我们的例子中是：E：2-SharePointServer2016Prequisites

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-15.png?raw=true "#")
 
Be patient as this process completes.

耐心等待此过程完成。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-16.png?raw=true "#")
 
Once this completes it will simply disappear. Just remember to go to the folder where you’re downloading the prerequisites and ensure they’ve been properly downloaded.

一旦完成，它就会消失。 只需记住转到你正在下载的必备组件的文件夹，并确保它们已正确下载。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-17.png?raw=true "#")
 
Step 08:
Mount the Sharepoint 2016 installation file. If you recall from Step 01 we put the file in the 01-SharePointServer2016 Folder. Take note of the Drive letter once after it’s mounted. You’ll need to know this for the next step.

第八步：
装载Sharepoint 2016安装文件。如果你记得，我们是在第一步中将文件放在01-SharePointServer2016文件夹中。安装后请记下驱动器号，下一步会需要。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-18.png?raw=true "#")
 
In this case it’s Drive F:

在这个例子中是Drive F：

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-19.png?raw=true "#")
 
Here is the Powershell script you can use to install Sharepoint 2016, including the Prerequisites.

以下是可用于安装Sharepoint 2016，包括必备组件的Powershell脚本。

#Directory path where SP 2016 RTM files are kept
$PreRequsInstallerPath= F:
 
#Directory path where SP 2016 Pre-requisites files are kept
$PreRequsFilesPath = E:2-SharePointServer2016Prequisites
 
Start-Process $PreRequsInstallerPathPrerequisiteInstaller.exe&quot; -Wait -ArgumentList`
/SQLNCli:`$PreRequsFilesPathsqlncli.msi``
/idfx11:`$PreRequsFilesPathMicrosoftIdentityExtensions-64.msi``
/Sync:`$PreRequsFilesPathSynchronization.msi``
/AppFabric:`$PreRequsFilesPathWindowsServerAppFabricSetup_x64.exe``
/kb3092423:`$PreRequsFilesPathAppFabric-KB3092423-x64-ENU.exe``
/MSIPCClient:`$PreRequsFilesPathsetup_msipc_x64.exe``
/wcfdataservices56:`$PreRequsFilesPathWcfDataServices.exe``
/odbc:`$PreRequsFilesPathmsodbcsql.msi`&quot; `
/msvcrt11:`$PreRequsFilesPathvc_redist.x64.exe``
/msvcrt14:`$PreRequsFilesPathvcredist_x64.exe``
/dotnetfx:`$PreRequsFilesPathNDP46-KB3045557-x86-x64-AllOS-ENU.exe`

I’m putting in an extra screenshot of the Powershell text in case the it gets butchered by autocorrect after posting it up to the blog. I want you to see it in it’s original form. By the way; that’s a monokai theme for Powershell. Eat it bitches!

我正准备添加一张Powershell文本的额外屏幕截图，以防发布到博客后自动更正（autocorrect）将其阻拦。我希望你能看到它原来的形式。 顺便说一句，这是Powershell的monokai主题。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-20.png?raw=true "#")
 
You can use the above script to create the .ps1 file. I simply used notepad, and pasted in the above text, and renamed the file to: Install_Sharepoint_2016.ps1. Keep in mind… After the installation completes it will immediately reboot the server. Technically this is the pre-installation phase so in hindsite I should have perhaps named this PreSharepoint_2016_Installer.ps1.

你可以使用上面的脚本来创建.ps1文件。我只用记事本，粘贴在上面的文本中，并将文件重命名为：Install_Sharepoint_2016.ps1。请记住......安装完成后，它将立即重启服务器。从技术上讲，这是预安装阶段，因此在hindsite
中我应该将其命名为PreSharepoint_2016_Installer.ps1。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-21.png?raw=true "#")
 
Once this is run you’ll get the following screen. Just click ‘Next’.

运行后，你将看到以下截图。 只需点击“Next”即可。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-22.png?raw=true "#")
 
Agree to the terms and click ‘Next’.

同意条款，并点击”Next”。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-23.png?raw=true "#")
 
Be patient as this process completes.

耐心等待此过程完成。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-24.png?raw=true "#")
 
Click ‘Finish’. Again; keep in mind… After you click Finish it will immediately reboot the server.

点击”Finish”。然后，请记住…点击完成后，它将立即重启服务器。

![#](images/ Installing-Sharepoint-2016-on-Windows-Server-2012-R2-using-SQL-Server-2014-SP1-CU6-25.png?raw=true "#")

 
The complete text base version of this information can be found at Microsoft Technet Here:
https://gallery.technet.microsoft.com/office/PreRequisites-for-7f719ff3
可以在Microsoft Technet上找到此信息的完整文本基础版本：
https://gallery.technet.microsoft.com/office/PreRequisites-for-7f719ff3

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")


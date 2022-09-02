# 写在最前：该仓库为 THFF 专用客户端，如需修改请前往[原始仓库](#原始仓库) #

# CnCNet 客户端 #

MonoGame / XNA CnCNet 客户端，一个在线和离线玩经典命令与征服游戏及其模组的平台。支持使用 [a CnCNet 游戏生成器](https://github.com/CnCNet/ts-patches) 设置和启动单人游戏和多人游戏。包括一个基于 IRC 的聊天客户端，具有私人消息传递、朋友列表、可配置的游戏大厅、灵活和可修改的 UI 图形等高级功能，以及游戏设置配置和跟踪比赛统计数据等附加功能。以及更多！

目标
--------

客户项目的主要目标是


* [泰伯利亚时代的黎明](http://www.moddb.com/mods/the-dawn-of-the-tiberium-age)
* [扭曲起义](http://www.moddb.com/mods/twisted-insurrection)
* [心灵终结](http://www.moddb.com/mods/mental-omega)
* [CnCNet 尤里的复仇](https://cncnet.org/yuris-revenge)


但是，客户端没有任何限制可以阻止将其合并到其他项目中。可以支持任何将 CnCNet 生成器用于 Tiberian Sun 和 Red Alert 2 的游戏或模组项目。其他几个项目也使用客户端或它的非官方分支，包括 [Tiberian Sun Client](https://www.moddb.com/mods/tiberian-sun-client)、[Project Phantom](https://www.moddb.com/mods/project-phantom), [YR Red-Resurrection](https://www.moddb.com/mods/yr-red-resurrection), [第二次泰伯利亚战争](https://www.moddb.com/mods/the-second-tiberium-war) 和 [CnC: Final War](https://www.moddb.com/mods/cncfinalwar)。

要求
------------

客户端有 3 个版本：Windows (DirectX11)、OpenGL 和 XNA。
* Windows 和 OpenGL 构建依赖于 .NET Framework 4.5 和 MonoGame。
* XNA 构建依赖于 .NET Framework 4.0 和 Microsoft 的 XNA Framework 4.0 Refresh。
  * [为 Visual Studio 2019 安装 XNA](http://flatredball.com/visual-studio-2019-xna-setup/)
  * [为 Visual Studio 2017 安装 XNA](http://flatredball.com/visual-studio-2017-xna-setup/)

为任何平台构建解决方案都需要 Visual Studio 2017 或更高版本。现代版本的 Visual Studio Code、MonoDevelop 或 Visual Studio for Mac 也可以工作（以及没有任何类型 IDE 的单独 MSBuild），但不受官方支持。

编译、调试和使用
------------------------------

* 编译本身很简单：假设您已经安装了先决条件，您可以使用 Visual Studio 打开解决方案并立即编译；该存储库包括 MonoGame 和其他必要的 DLL，用于快速编译。
* 当构建为调试版本时，客户端可执行文件应与目标项目的主游戏可执行文件位于同一目录中。资源应存在于同一目录中的“资源”子目录中。存储库包含用于复制它们的示例资源和构建后命令，以便您只需点击 Visual Studio 中的“调试”按钮即可立即在调试模式下运行客户端。
* 在发布模式下构建时，客户端可执行文件期望驻留在“资源”子目录本身中。在目标项目中，每个平台的客户端可执行文件分别命名为“clientdx.exe”、“clientogl.exe”和“clientxna.exe”。
* `BuildScripts` 目录有自动构建脚本，为所有 3 个平台构建客户端，并将输出文件复制到项目根目录中名为 `Compiled` 的文件夹中。然后，您可以将此 `Compiled` 目录的内容复制到任何目标项目的 `Resources` 子目录中。请注意，默认情况下，构建脚本还构建客户端的 XNA 版本，这需要安装 XNA Framework 4.0 Refresh。如果您不想安装 XNA，则需要修改 `BuildGame.bat` 以保留 XNAFramework 构建。

最终用户使用
--------------

对于运行 Vista 或更新版本 Windows 的最终用户，首选 MonoGame (DirectX11) 构建。 MonoGame 构建无法在 Windows XP 上运行，因此 XNA 构建适用于 XP 用户以及 GPU 无法正确支持 DX11 的用户。

MonoGame WindowsGL / DesktopGL 构建主要用于实验性 Linux 和 Mac 支持。

客户端启动器
---------------

此存储库不包含客户端启动器（例如，泰伯利亚时代黎明中的“DTA.exe”），它选择哪个平台的客户端可执行文件最适合每个用户的系统。为此，请参阅 [dta-mg-client-launcher](https://github.com/CnCNet/dta-mg-client-launcher)。

分支
--------

目前只有一个主要的活跃分支。 `master` 是开发发生的地方，虽然事情应该相当稳定，但偶尔也会有错误。

原始仓库
------------
[Rampastring
/
dta-xna-cncnet-client](https://github.com/Rampastring/dta-xna-cncnet-client)

截图
------------

![Screenshot](cncnetchatlobby.png?raw=true "CnCNet IRC 聊天大厅")
![Screenshot](cncnetgamelobby.png?raw=true "CnCNet 游戏大厅")

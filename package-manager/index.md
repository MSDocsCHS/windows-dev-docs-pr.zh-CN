---
title: Windows 包管理器
description: Windows 包管理器是一个包括一个命令行工具和一组服务的全面的包管理器解决方案，用于在 Windows 上安装应用程序。
ms.date: 10/30/2023
ms.topic: overview
ms.orig.link: https://learn.microsoft.com/windows/package-manager/
---

# Windows 包管理器

Windows 包管理器是一个全面的 [包管理器解决方案](#理解包管理器)，由一个命令行工具（WinGet）和一组用于在 Windows 设备上安装应用程序的服务组成。

Windows 包管理器对以下用户有所帮助：

- 希望通过命令行来管理他们的软件应用程序的 [开发者](#适用于开发者的-windows-包管理器)。
- 希望分发软件的 [独立软件供应商 (ISV)](#适用于-ISV-软件分发的-windows-包管理器)。
- 希望自动化设备设置并维护安全工作环境的 [企业组织](#适用于企业安全的-windows-包管理器)。

## 理解包管理器

包管理器是一个用于自动化安装、升级、配置和使用软件的系统或一组工具。大多数包管理器都是为发现和安装开发工具而设计的。

理想情况下，开发人员使用包管理器来指定他们需要为给定项目开发解决方案的工具的先决条件。然后，包管理器遵循声明性指令来安装和配置工具。包管理器减少了准备环境所需的时间，并有助于确保在计算机上安装相同版本的程序包。

第三方包管理器可以利用 [Microsoft 社区包清单存储库](package/repository.md) 来扩充其软件目录。

## 适用于开发者的 Windows 包管理器

开发者使用 **winget** 命令行工具来发现、安装、升级、删除和配置一组经过筛选的应用程序。在安装完成后，开发者可以通过 Windows 终端、PowerShell 或命令提示符访问 **winget**。

有关详细信息，请参阅 [使用 winget 工具安装和管理应用程序](winget/index.md)。

有关 winget 的视频演示，请参阅 [Windows 包管理器简介](/shows/open-at-microsoft/intro-to-windows-package-manager)。

有关最新公告和版本更新，请参阅 [Windows 命令行博客](https://devblogs.microsoft.com/commandline/)，其中包括：

- [Windows 包管理器 1.4](https://devblogs.microsoft.com/commandline/windows-package-manager-1-4/)
- [Windows 包管理器 1.3](https://devblogs.microsoft.com/commandline/windows-package-manager-1-3/)
- [Windows 包管理器 1.2](https://devblogs.microsoft.com/commandline/windows-package-manager-1-2/)
- [Windows 包管理器 1.1](https://devblogs.microsoft.com/commandline/windows-package-manager-1-1/)
- [Windows 包管理器 1.0](https://devblogs.microsoft.com/commandline/windows-package-manager-1-0/)

## 适用于 ISV 软件分发的 Windows 包管理器

独立软件供应商 (ISV) 可以使用 Windows 包管理器作为包含其工具和应用程序的软件包的分发渠道。为了将软件包 (包含 .msix、.msi 或 .exe 安装程序) 提交到 Windows 包管理器，我们在 GitHub 上提供了开源的 **Microsoft 社区包清单存储库**。ISV 可以在其中上传 [包清单](package/manifest.md)。我们在考虑后会决定是否将其软件包包括在 Windows 包管理器中。清单会被自动验证，也可能会被手动审核。

有关详细信息，请参阅 [将软件包提交到 Windows 包管理器](package/repository.md)。

## 适用于企业安全的 Windows 包管理器

WinGet 客户端可被用于在多台计算机上安装和管理应用程序。负责设置企业工作环境的人员，例如 IT 管理员或安全分析员，可能会使用 [Microsoft Intune](/mem/intune/) 通过“组策略”设置来管理安全性。

为了保持持续的安全更新，WinGet 客户端是通过 Microsoft Store 发布的，并使用 [“msstore” 源](./winget/source.md) 从 Microsoft Store 安装应用程序，并应用“证书固定”以确保连接是安全的，并且是与正确的终结点建立的。

企业组织应用的组策略可能使用防火墙进行 SSL 检查，导致 WinGet 客户端中出现连接错误。

为此，Windows 包管理器桌面安装程序支持一个名为：“BypassCertificatePinningForMicrosoftStore”的策略设置。此策略控制 Windows 包管理器在与 Microsoft Store 源建立连接时是否验证 Microsoft Store 证书哈希与已知 Microsoft Store 证书匹配。此策略的选项包括：

- **未配置 (默认)**：如果不配置此策略，将遵循 Windows 包管理器管理员设置。我们建议将此策略保留为未配置默认值，除非您有特定需求需要更改。
- **启用**：如果启用此策略，Windows 包管理器将绕过 Microsoft Store 证书验证。
- **禁用**：如果禁用此策略，Windows 包管理器将验证 Microsoft Store 证书是否有效并属于 Microsoft Store，然后再与 Microsoft Store 源通信。

“证书固定”确保包管理器与 Microsoft Store 的连接是安全的，有助于避免与第三方插入攻击有关的风险，例如中间人 (MITM) 攻击，其中第三方将自己插入客户端 (用户) 和服务器 (应用程序) 之间，以秘密拦截通信流以窃取敏感数据，例如登录凭据等。禁用“证书固定” (启用绕过) 可能会使您的组织在该方面暴露于危险之中，应当避免。

有关为您的企业组织设置组策略的更多信息，请参阅 [Microsoft Intune 文档](/mem/intune/)。

## 下一步

- [使用 winget 工具安装和管理应用程序](winget/index.md)
- [将软件包提交到 Windows 包管理器](package/index.md)

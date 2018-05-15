---
title: Install and configure Azure PowerShell on macOS and Linux | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use on macOS and Linux.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/12/2018
---
# Install and configure Azure PowerShell on macOS and Linux

It is now possible to install PowerShell Core v6 and Azure PowerShell on non-Windows platforms.
The process of installing Azure PowerShell on macOS and Linux is not that different from Windows,
however, you must first install PowerShell Core v6.

> [!NOTE]

> At this time, both PowerShell Core v6 and Azure PowerShell for .NET Core are still in beta.
> Support for these products is limited. If you have problems or discover bugs, please file Issues
> in GitHub.
>
> * [Issues for PowerShell Core v6](https://github.com/PowerShell/PowerShell/issues)
> * [Issues for Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## Step 1: Install PowerShell Core v6

The process of installing PowerShell Core v6 varies depending on the target operating system.
While it is possible to install PowerShell Core v6 on Windows, this article focuses on macOS and
Linux. If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md)
article for Windows.

Installing **PowerShell Core v6** on Linux or macOS varies depending on the Linux distribution and OS version.
Detailed instructions can be found in the following articles:

- [Installing PowerShell Core on macOS](/powershell/scripting/setup/installing-powershell-core-on-macos)
- [Installing PowerShell Core on Linux](/powershell/scripting/setup/installing-powershell-core-on-linux)

## Step 2: Install Azure PowerShell for .NET Core

PowerShell Core v6 comes with the PowerShellGet module already installed. This makes it easy to
install any module that is published to the PowerShell Gallery. To install Azure PowerShell, open a
new PowerShell session and run the following command:

```powershell
Install-Module AzureRM.NetCore
```

## Step 3: Load the AzureRM.Netcore module

Once the module is installed, you need to load the module into your PowerShell session. Modules are
loaded using the `Import-Module` cmdlet, as follows:

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

After the import completes, you can test your newly installed and module by attempting to sign into
Azure using the following command:

```powershell
Connect-AzureRmAccount
```

The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the
provided code.

## Available cmdlets

The Azure PowerShell modules for .NET Standard are still in development. These modules do not
provide the full set of cmdlets that are available for the Windows version of the modules. The
following functions are implemented in AzureRM.Netcore modules:

* Account management
  - Login with Microsoft account, Organizational account, or Service Principal through Microsoft
    Azure Active Directory
  - Save Credentials to disk with Save-AzureRmContext and load saved credentials using
    Import-AzureRmContext
* Environment
  - Get the different out-of-box Microsoft Azure environments
  - Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)
* Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.
  - Virtual Machine
  - App Service (Websites)
  - SQL Database
  - Storage
  - Network

## Next Steps

For more information about using Azure PowerShell, see the
[Get started with Azure PowerShell](get-started-azureps.md) article.

---
title: Installieren von .NET Core auf CentOS Linux 8 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die .NET Core-Runtime auf CentOS 8 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728504"
---
# <a name="centos-8-package-manager---install-net-core"></a><span data-ttu-id="f977d-103">CentOS 8-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="f977d-103">CentOS 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="f977d-104">In diesem Artikel wird beschrieben, wie Sie .NET Core mit einem Paket-Manager auf CentOS 8 installieren.</span><span class="sxs-lookup"><span data-stu-id="f977d-104">This article describes how to use a package manager to install .NET Core on CentOS 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f977d-105">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f977d-105">Install the .NET Core SDK</span></span>

<span data-ttu-id="f977d-106">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f977d-106">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f977d-107">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="f977d-107">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="f977d-108">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f977d-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f977d-109">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="f977d-109">Install the .NET Core Runtime</span></span>

<span data-ttu-id="f977d-110">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f977d-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f977d-111">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="f977d-111">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

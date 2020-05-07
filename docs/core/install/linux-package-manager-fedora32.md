---
title: '.NET Core: Installieren von .NET Core auf Fedora 32 mit einem Paket-Manager'
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die .NET Core-Runtime auf Fedora 32 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624951"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="12ba7-103">Fedora 32-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="12ba7-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="12ba7-104">In diesem Artikel wird beschrieben, wie Sie .NET Core mit einem Paket-Manager auf Fedora 32 installieren.</span><span class="sxs-lookup"><span data-stu-id="12ba7-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="12ba7-105">Ab Fedora 32 ist .NET Core 3.1 in den Standardpaketrepositorys in Fedora verfügbar.</span><span class="sxs-lookup"><span data-stu-id="12ba7-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="12ba7-106">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="12ba7-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="12ba7-107">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="12ba7-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="12ba7-108">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="12ba7-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="12ba7-109">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="12ba7-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="12ba7-110">Installieren Sie die ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="12ba7-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="12ba7-111">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="12ba7-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="12ba7-112">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="12ba7-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="12ba7-113">Installieren Sie die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="12ba7-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="12ba7-114">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="12ba7-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="12ba7-115">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="12ba7-115">How to install other versions</span></span>

<span data-ttu-id="12ba7-116">Installieren Sie das [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) oder die [.NET Core-Runtime](runtime.md?pivots=os-linux#download-and-manually-install) manuell, um andere Versionen von .NET Core zu installieren.</span><span class="sxs-lookup"><span data-stu-id="12ba7-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>

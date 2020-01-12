---
title: Installieren von .NET Core auf Linux RHEL 8.1 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 8.1 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714374"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="8c197-103">RHEL 8.1-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="8c197-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="8c197-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 8.1 installieren.</span><span class="sxs-lookup"><span data-stu-id="8c197-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="8c197-105">.NET Core 3.1 ist für RHEL 8.1 noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c197-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="8c197-106">RHEL 8.0 umfasst nicht .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8c197-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="8c197-107">Verwenden Sie den Befehl `yum upgrade`, um ein Update auf RHEL 8.1 durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8c197-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="8c197-108">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="8c197-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="8c197-109">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8c197-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="8c197-110">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="8c197-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="8c197-111">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="8c197-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="8c197-112">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8c197-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="8c197-113">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="8c197-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="8c197-114">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="8c197-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="8c197-115">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8c197-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="8c197-116">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="8c197-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="8c197-117">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="8c197-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="8c197-118">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8c197-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="8c197-119">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="8c197-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="8c197-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c197-120">See also</span></span>

- [<span data-ttu-id="8c197-121">Verwenden von .NET Core 3.0 auf Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="8c197-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)

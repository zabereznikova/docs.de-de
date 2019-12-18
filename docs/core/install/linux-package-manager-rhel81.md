---
title: Installieren von .NET Core auf Linux RHEL 8.1 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 8.1 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 3ef639d5b76e81856ec8370d10e098c455ca8b3d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998912"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="6a3aa-103">RHEL 8.1-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a3aa-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="6a3aa-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 8.1 installieren.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="6a3aa-105">.NET Core 3.1 ist für RHEL 8.1 noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="6a3aa-106">RHEL 8.0 umfasst nicht .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="6a3aa-107">Verwenden Sie den Befehl `yum upgrade`, um ein Update auf RHEL 8.1 durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="6a3aa-108">RHEL 8.0 umfasst nicht .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-108">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="6a3aa-109">Verwenden Sie den Befehl `yum upgrade`, um ein Update auf RHEL 8.1 durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-109">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="6a3aa-110">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="6a3aa-110">Register your Red Hat subscription</span></span>

<span data-ttu-id="6a3aa-111">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-111">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="6a3aa-112">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="6a3aa-112">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="6a3aa-113">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="6a3aa-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="6a3aa-114">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-114">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="6a3aa-115">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-115">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="6a3aa-116">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="6a3aa-116">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="6a3aa-117">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-117">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="6a3aa-118">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-118">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="6a3aa-119">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="6a3aa-119">Install the .NET Core Runtime</span></span>

<span data-ttu-id="6a3aa-120">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-120">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="6a3aa-121">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="6a3aa-121">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="6a3aa-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a3aa-122">See also</span></span>

- [<span data-ttu-id="6a3aa-123">Verwenden von .NET Core 3.0 auf Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="6a3aa-123">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)

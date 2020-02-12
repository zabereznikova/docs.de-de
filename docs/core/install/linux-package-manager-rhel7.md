---
title: Installieren von .NET Core auf Linux RHEL 7 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 7 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 4f85ed3da8a434fcd5b6ee88491daf623c3c8b31
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980183"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="fb49b-103">RHEL 7-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="fb49b-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="fb49b-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 7 installieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="fb49b-105">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="fb49b-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="fb49b-106">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="fb49b-107">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="fb49b-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="fb49b-108">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="fb49b-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="fb49b-109">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="fb49b-110">Führen Sie in Ihrem Terminal die folgenden Befehle aus, um den dotnet-Kanal RHEL 7 zu aktivieren und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="fb49b-111">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="fb49b-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="fb49b-112">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="fb49b-113">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="fb49b-113">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="fb49b-114">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="fb49b-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="fb49b-115">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb49b-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="fb49b-116">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="fb49b-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a><span data-ttu-id="fb49b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb49b-117">See also</span></span>

- [<span data-ttu-id="fb49b-118">Verwenden von .NET Core 3.1 unter Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="fb49b-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)

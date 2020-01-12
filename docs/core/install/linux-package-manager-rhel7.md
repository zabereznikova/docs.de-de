---
title: Installieren von .NET Core auf Linux RHEL 7 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 7 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: bcc41bfcd7c6d03038952e3faaf07952c3deb69d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715535"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="5b6b2-103">RHEL 7-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="5b6b2-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="5b6b2-104">In diesem Artikel wird beschrieben, wie Sie mit einem Paket-Manager .NET Core auf RHEL 7 installieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="5b6b2-105">.NET Core 3.1 ist für RHEL 7 noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="5b6b2-106">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="5b6b2-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="5b6b2-107">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="5b6b2-108">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="5b6b2-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5b6b2-109">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5b6b2-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="5b6b2-110">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="5b6b2-111">Führen Sie in Ihrem Terminal die folgenden Befehle aus, um den dotnet-Kanal RHEL 7 zu aktivieren und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5b6b2-112">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="5b6b2-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="5b6b2-113">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="5b6b2-114">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-114">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5b6b2-115">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="5b6b2-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="5b6b2-116">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="5b6b2-117">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5b6b2-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="5b6b2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b6b2-118">See also</span></span>

- [<span data-ttu-id="5b6b2-119">Verwenden von .NET Core 3.0 auf Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="5b6b2-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)

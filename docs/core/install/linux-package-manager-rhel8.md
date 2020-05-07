---
title: Installieren von .NET Core auf Linux RHEL 8 mit einem Paket-Manager (.NET Core)
description: Verwenden Sie einen Paket-Manager, um das .NET Core SDK und die -Runtime auf RHEL 8 zu installieren.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: 8829e842e920e6abd4184b5140f80bb016acace2
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728239"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="f9393-103">RHEL 8-Paket-Manager: Installieren von .NET Core</span><span class="sxs-lookup"><span data-stu-id="f9393-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="f9393-104">In diesem Artikel wird beschrieben, wie Sie .NET Core mit einem Paket-Manager auf RHEL 8 (Red Hat Enterprise Linux) installieren.</span><span class="sxs-lookup"><span data-stu-id="f9393-104">This article describes how to use a package manager to install .NET Core on Red Hat Enterprise Linux (RHEL) 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="f9393-105">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="f9393-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="f9393-106">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f9393-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="f9393-107">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="f9393-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f9393-108">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f9393-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="f9393-109">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun das .NET Core SDK installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9393-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="f9393-110">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f9393-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f9393-111">Installieren der ASP.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="f9393-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="f9393-112">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die ASP.NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9393-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="f9393-113">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f9393-113">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f9393-114">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="f9393-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="f9393-115">Nachdem Sie sich beim Abonnement-Manager registriert haben, können Sie nun die .NET Core-Runtime installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9393-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="f9393-116">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f9393-116">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f9393-117">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="f9393-117">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="see-also"></a><span data-ttu-id="f9393-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9393-118">See also</span></span>

- [<span data-ttu-id="f9393-119">Verwenden von .NET Core 3.1 unter Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="f9393-119">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)

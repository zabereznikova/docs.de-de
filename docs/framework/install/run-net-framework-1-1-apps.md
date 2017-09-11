---
title: "Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10"
ms.custom: 
ms.date: 05/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: c7b53a842dc4f9b6bfc04e058411e4a6d11a7bd1
ms.contentlocale: de-de
ms.lasthandoff: 08/05/2017

---

# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="3bfd3-102">Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10</span><span class="sxs-lookup"><span data-stu-id="3bfd3-102">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="3bfd3-103">.NET Framework 1.1 wird von den Betriebssystemen [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-103">The .NET Framework 1.1 is not supported on the [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or the Windows 10 operating systems.</span></span> <span data-ttu-id="3bfd3-104">In manchen Fällen wird ausdrücklich angegeben, dass .NET Framework 1.1 zum Ausführen einer App notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-104">In some cases, the .NET Framework 1.1 is specifically identified as required for an app to run.</span></span> <span data-ttu-id="3bfd3-105">In solchen Fällen sollten Sie sich an den unabhängigen Softwareanbieter wenden und die App so aktualisieren lassen, dass sie unter [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] oder einer höheren Version ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-105">In those cases, you should contact your independent software vendor (ISV) to have the app upgraded to run on the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] or later version.</span></span> <span data-ttu-id="3bfd3-106">Weitere Informationen finden Sie unter [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="3bfd3-106">For additional information, see [Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="3bfd3-107">Installieren von .NET Framework 1.1 von einem Datenträger CD oder über das Download Center</span><span class="sxs-lookup"><span data-stu-id="3bfd3-107">Install the .NET Framework 1.1 from a CD or Download Center</span></span>

<span data-ttu-id="3bfd3-108">NET Framework 1.1 kann unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht manuell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-108">It isn't possible to manually install the .NET Framework 1.1 on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or Windows 10.</span></span> <span data-ttu-id="3bfd3-109">Er wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-109">It is no longer supported.</span></span> <span data-ttu-id="3bfd3-110">Wenn Sie versuchen, das Paket zu installieren, wird die folgende Fehlermeldung angezeigt: "Setup kann nicht fortgesetzt werden, da diese Version von .NET Framework mit einer zuvor installierten Version inkompatibel ist".</span><span class="sxs-lookup"><span data-stu-id="3bfd3-110">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="3bfd3-111">Installieren Sie [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22), um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-111">To solve this problem, install the [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="3bfd3-112">Diese Version enthält .NET Framework 2.0 (die Folgeversion von .NET Framework 1.1), die unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] und Windows 10 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-112">This version includes the .NET Framework 2.0 (the release that follows the .NET Framework 1.1), which is supported on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], and Windows 10.</span></span> <span data-ttu-id="3bfd3-113">Sie sollten immer versuchen, zunächst die App zu installieren, um herauszufinden, ob automatisch eine Aktualisierung auf eine höhere Version von .NET Framework durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-113">You should always try to install the app first to determine if it will automatically be updated to a later version of the .NET Framework.</span></span> <span data-ttu-id="3bfd3-114">Wenn dies nicht der Fall ist, wenden Sie sich an den unabhängigen Softwareanbieter um ein Update für die App zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3bfd3-114">If it does not, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bfd3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bfd3-115">See also</span></span>

<span data-ttu-id="3bfd3-116">[Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="3bfd3-116">[Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span></span>


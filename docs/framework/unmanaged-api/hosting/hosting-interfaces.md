---
title: Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e330e0d06077d1eef63cf44f31bbcbf7c3431b59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985542"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="6557a-102">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6557a-102">Hosting Interfaces</span></span>
<span data-ttu-id="6557a-103">In diesem Abschnitt wird beschrieben, die Schnittstellen, die nicht verwaltete Hosts können die common Language Runtime (CLR) in ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="6557a-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="6557a-104">Die .NET Framework Version 2.0-Hostingschnittstellen Vorrang vor den .NET Framework Version 1.0 und 1.1-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6557a-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="6557a-105">Es gibt bedeutende Unterschiede zwischen den beiden Sätzen von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6557a-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="6557a-106">Mischen sie kann unerwartetes Verhalten verursachen und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6557a-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="6557a-107">Die .NET Framework-Versionen 3.0 und 3.5 verwenden die .NET Framework Version 2.0-Hostingschnittstellen und Hostingfunktionen führen.</span><span class="sxs-lookup"><span data-stu-id="6557a-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="6557a-108">Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Hostschnittstellen in die .NET Framework 2.0-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6557a-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6557a-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6557a-109">In This Section</span></span>  
 [<span data-ttu-id="6557a-110">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="6557a-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="6557a-111">Beschreibt die hosting-Schnittstellen in .NET Framework, Version 1.0 und 1.1 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6557a-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="6557a-112">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6557a-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="6557a-113">Beschreibt die hosting-Schnittstellen in .NET Framework, Version 2.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6557a-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="6557a-114">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6557a-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="6557a-115">Beschreibt die in eingeführt Hostingschnittstellen der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6557a-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6557a-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6557a-116">Related Sections</span></span>  
 [<span data-ttu-id="6557a-117">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="6557a-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="6557a-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="6557a-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="6557a-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6557a-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="6557a-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="6557a-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="6557a-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="6557a-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="6557a-122">[Laufzeithosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6557a-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>

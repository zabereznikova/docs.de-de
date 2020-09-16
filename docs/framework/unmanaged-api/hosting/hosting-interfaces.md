---
title: Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: b1459bf78276abe0daefd7a7ee814841f3c65dfb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550663"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="cd547-102">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd547-102">Hosting Interfaces</span></span>
<span data-ttu-id="cd547-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="cd547-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="cd547-104">Die .NET Framework-Hostingschnittstellen der Version 2,0 ersetzen die Schnittstellen .NET Framework der Version 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="cd547-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="cd547-105">Es gibt bedeutende Unterschiede zwischen den beiden Schnittstellen Sätzen.</span><span class="sxs-lookup"><span data-stu-id="cd547-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="cd547-106">Das Mischen kann zu unerwartetem Verhalten führen und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="cd547-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="cd547-107">In den .NET Framework Versionen 3,0 und 3,5 werden die .NET Framework Version 2,0-Hostingschnittstellen verwendet, und es werden keine Hostingfeatures eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd547-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="cd547-108">Die .NET Framework 4-Hostingschnittstellen ersetzen die .NET Framework 2,0-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="cd547-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cd547-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd547-109">In This Section</span></span>  
 [<span data-ttu-id="cd547-110">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="cd547-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="cd547-111">Beschreibt die Hostingschnittstellen, die in den .NET Framework Versionen 1,0 und 1,1 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd547-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="cd547-112">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd547-112">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="cd547-113">Beschreibt die Hostingschnittstellen, die in der .NET Framework Version 2,0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd547-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="cd547-114">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd547-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="cd547-115">Beschreibt die Hostingschnittstellen, die in der .NET Framework 4 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd547-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cd547-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cd547-116">Related Sections</span></span>  
 [<span data-ttu-id="cd547-117">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="cd547-117">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="cd547-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="cd547-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="cd547-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="cd547-119">Hosting Enumerations</span></span>](hosting-enumerations.md)  
  
 [<span data-ttu-id="cd547-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="cd547-120">Hosting Structures</span></span>](hosting-structures.md)  
  
 [<span data-ttu-id="cd547-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="cd547-121">Hosting</span></span>](index.md)  
  
 <span data-ttu-id="cd547-122">[Laufzeithosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd547-122">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>

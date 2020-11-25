---
title: Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: f82301da1813b8d50deebf4452d8c07809c186c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721802"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="de5c5-102">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="de5c5-102">Hosting Interfaces</span></span>

<span data-ttu-id="de5c5-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="de5c5-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="de5c5-104">Die .NET Framework-Hostingschnittstellen der Version 2,0 ersetzen die Schnittstellen .NET Framework der Version 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="de5c5-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="de5c5-105">Es gibt bedeutende Unterschiede zwischen den beiden Schnittstellen Sätzen.</span><span class="sxs-lookup"><span data-stu-id="de5c5-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="de5c5-106">Das Mischen kann zu unerwartetem Verhalten führen und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="de5c5-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="de5c5-107">In den .NET Framework Versionen 3,0 und 3,5 werden die .NET Framework Version 2,0-Hostingschnittstellen verwendet, und es werden keine Hostingfeatures eingeführt.</span><span class="sxs-lookup"><span data-stu-id="de5c5-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="de5c5-108">Die .NET Framework 4-Hostingschnittstellen ersetzen die .NET Framework 2,0-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="de5c5-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="de5c5-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="de5c5-109">In This Section</span></span>  

 [<span data-ttu-id="de5c5-110">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="de5c5-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="de5c5-111">Beschreibt die Hostingschnittstellen, die in den .NET Framework Versionen 1,0 und 1,1 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="de5c5-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="de5c5-112">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="de5c5-112">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="de5c5-113">Beschreibt die Hostingschnittstellen, die in der .NET Framework Version 2,0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="de5c5-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="de5c5-114">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="de5c5-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="de5c5-115">Beschreibt die Hostingschnittstellen, die in der .NET Framework 4 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="de5c5-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de5c5-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="de5c5-116">Related Sections</span></span>  

 [<span data-ttu-id="de5c5-117">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="de5c5-117">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="de5c5-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="de5c5-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="de5c5-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="de5c5-119">Hosting Enumerations</span></span>](hosting-enumerations.md)  
  
 [<span data-ttu-id="de5c5-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="de5c5-120">Hosting Structures</span></span>](hosting-structures.md)  
  
 [<span data-ttu-id="de5c5-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="de5c5-121">Hosting</span></span>](index.md)  
  
 <span data-ttu-id="de5c5-122">[Laufzeithosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="de5c5-122">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>

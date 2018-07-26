---
title: COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244663"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="894a0-102">COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="894a0-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="894a0-103">Wenn Sie COM-Objekte und .NET Framework-Objekte in der gleichen Anwendung verwenden möchten, müssen Sie behandeln die Unterschiede wie die Objekte im Arbeitsspeicher vorhanden.</span><span class="sxs-lookup"><span data-stu-id="894a0-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="894a0-104">.NET Framework-Objekt befindet sich im verwalteten Speicher, der Arbeitsspeicher, die von der common Language Runtime gesteuert, von der Runtime verschoben werden kann, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="894a0-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="894a0-105">Ein COM-Objekt befindet sich im nicht verwalteten Speicher und nicht an einen anderen Speicherort verschieben soll.</span><span class="sxs-lookup"><span data-stu-id="894a0-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="894a0-106">Visual Studio und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] bieten Tools zum Steuern der Interaktion dieser verwalteten und nicht verwalteten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="894a0-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="894a0-107">Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="894a0-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="894a0-108">Zusätzlich zur Verwendung von COM-Objekte in .NET-Anwendungen, sollten Sie auch Visual Basic verwenden, zum Entwickeln von Objekten aus nicht verwaltetem Code über COM zugegriffen werden kann</span><span class="sxs-lookup"><span data-stu-id="894a0-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="894a0-109">Die Links auf dieser Seite die Details auf die Interaktionen zwischen COM und .NET Framework-Objekte.</span><span class="sxs-lookup"><span data-stu-id="894a0-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="894a0-110">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="894a0-110">Related Sections</span></span>  
 [<span data-ttu-id="894a0-111">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="894a0-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="894a0-112">Enthält Links zu Themen, in denen COM-Interoperabilität in Visual Basic, einschließlich COM-Objekten, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="894a0-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="894a0-113">COM-Interop-Wrapperfehler</span><span class="sxs-lookup"><span data-stu-id="894a0-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="894a0-114">Beschreibt die folgen und Optionen an, wenn das Projektsystem einen COM-Interoperabilität-Wrapper für eine bestimmte Komponente erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="894a0-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="894a0-115">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="894a0-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="894a0-116">Kurz einige der Probleme Interaktion zwischen verwaltetem und nicht verwaltetem Code beschrieben, und enthält Links für weitere Studien.</span><span class="sxs-lookup"><span data-stu-id="894a0-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="894a0-117">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="894a0-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="894a0-118">Erläutert, Runtime callable Wrapper, die verwalteten Code zum Aufrufen von COM-Methoden zu ermöglichen, und COM callable Wrapper, die COM-Clients .NET Objekt-Methoden aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="894a0-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="894a0-119">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="894a0-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="894a0-120">Enthält Links zu Themen, in denen COM-Interoperabilität in Bezug auf Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshalling.</span><span class="sxs-lookup"><span data-stu-id="894a0-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="894a0-121">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="894a0-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="894a0-122">Beschreibt die Tools, die Sie verwenden können, um die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="894a0-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>

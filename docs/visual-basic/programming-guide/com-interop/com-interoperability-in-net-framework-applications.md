---
title: "COM-Interoperabilität in .NET Framework Applications (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6b68f35c1c63e2d7d229f89336b86c4a062e5ec9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="78c61-102">COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78c61-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="78c61-103">Wenn Sie COM-Objekte und .NET Framework-Objekte in der gleichen Anwendung verwenden möchten, müssen Sie auf die Unterschiede zwischen wie die Objekte im Arbeitsspeicher vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="78c61-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="78c61-104">.NET Framework-Objekt befindet sich im verwalteten Speicher – der Arbeitsspeicher, die von der common Language Runtime gesteuert, durch die Common Language Runtime verschoben werden kann, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="78c61-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="78c61-105">Ein COM-Objekt wird befindet sich im nicht verwalteten Speicher und nicht an einen anderen Speicherort verschieben.</span><span class="sxs-lookup"><span data-stu-id="78c61-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="78c61-106">und die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] bieten Tools zum Steuern der Interaktion dieser verwalteten und nicht verwalteten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="78c61-106"> and the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="78c61-107">Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span><span class="sxs-lookup"><span data-stu-id="78c61-107">For more information about managed code, see [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span></span>  
  
 <span data-ttu-id="78c61-108">Neben der Verwendung von COM-Objekten in .NET-Anwendungen können Sie möglicherweise auch verwenden möchten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] zum Entwickeln von Objekten aus nicht verwaltetem Code über COM zugegriffen werden kann</span><span class="sxs-lookup"><span data-stu-id="78c61-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="78c61-109">Die Links auf dieser Seite enthalten Details zu den Interaktionen zwischen COM- und .NET Framework-Objekten.</span><span class="sxs-lookup"><span data-stu-id="78c61-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="78c61-110">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="78c61-110">Related Sections</span></span>  
 [<span data-ttu-id="78c61-111">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="78c61-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="78c61-112">Enthält Links zu Themen über COM-Interoperabilität in Visual Basic, darunter COM-Objekte, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="78c61-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="78c61-113">COM-Interop-Wrapperfehler</span><span class="sxs-lookup"><span data-stu-id="78c61-113">COM Interop Wrapper Error</span></span>](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="78c61-114">Beschreibt die folgen und Optionen, wenn das Projektsystem einen COM-Interoperabilität-Wrapper für eine bestimmte Komponente erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="78c61-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="78c61-115">Interoperation mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="78c61-115">Interoperating with Unmanaged Code</span></span>](https://msdn.microsoft.com/library/sd10k43k)  
 <span data-ttu-id="78c61-116">Kurz beschreibt einige der Probleme für die Interaktion zwischen verwaltetem und nicht verwaltetem Code und enthält Links zum Abrufen weiterer Informationen.</span><span class="sxs-lookup"><span data-stu-id="78c61-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="78c61-117">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="78c61-117">COM Wrappers</span></span>](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 <span data-ttu-id="78c61-118">Erläutert, Runtime callable Wrapper, die verwalteten Code zum Aufrufen von COM-Methoden ermöglichen, sowie COM callable Wrapper, die COM-Clients Aufrufen von.</span><span class="sxs-lookup"><span data-stu-id="78c61-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="78c61-119">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="78c61-119">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="78c61-120">Enthält Links zu Themen über COM-Interoperabilität in Bezug auf den Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshalling.</span><span class="sxs-lookup"><span data-stu-id="78c61-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="78c61-121">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="78c61-121">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 <span data-ttu-id="78c61-122">Beschreibt das Tool, das Sie verwenden können, konvertiert die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly.</span><span class="sxs-lookup"><span data-stu-id="78c61-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>

---
title: "COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28ec54dc062d4fdea4836b0ecc8699982dace623
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="92f0b-102">COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92f0b-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="92f0b-103">Wenn Sie COM-Objekte und .NET Framework-Objekte in derselben Anwendung verwenden möchten, müssen Sie behandeln die Unterschiede in wie die Objekte im Arbeitsspeicher vorhanden.</span><span class="sxs-lookup"><span data-stu-id="92f0b-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="92f0b-104">.NET Framework-Objekt befindet sich im verwalteten Speicher – der Arbeitsspeicher, die von der common Language Runtime gesteuert – und von der Runtime verschoben werden kann, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="92f0b-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="92f0b-105">Ein COM-Objekt befindet sich im nicht verwalteten Speicher und ist nicht dazu gedacht, die an einen anderen Speicherort verschieben.</span><span class="sxs-lookup"><span data-stu-id="92f0b-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="92f0b-106">und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] bieten Tools steuern Sie die Interaktion dieser verwalteten und nicht verwalteten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="92f0b-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="92f0b-107">Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="92f0b-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="92f0b-108">Zusätzlich zur Verwendung von COM-Objekten in .NET-Anwendungen können Sie möglicherweise auch verwenden möchten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zum Entwickeln von Objekten aus nicht verwaltetem Code durch COM zugegriffen werden kann</span><span class="sxs-lookup"><span data-stu-id="92f0b-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="92f0b-109">Die Links auf dieser Seite enthalten Details zu den Interaktionen zwischen COM- und .NET Framework-Objekten.</span><span class="sxs-lookup"><span data-stu-id="92f0b-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="92f0b-110">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="92f0b-110">Related Sections</span></span>  
 [<span data-ttu-id="92f0b-111">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="92f0b-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="92f0b-112">Enthält Links zu Themen über COM-Interoperabilität in Visual Basic, z. B. com-Objekte, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="92f0b-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="92f0b-113">COM-Interop-Wrapperfehler</span><span class="sxs-lookup"><span data-stu-id="92f0b-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="92f0b-114">Beschreibt die folgen und Optionen an, wenn das Projektsystem einen COM-Interoperabilität-Wrapper für eine bestimmte Komponente erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="92f0b-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="92f0b-115">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="92f0b-115">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)  
 <span data-ttu-id="92f0b-116">Beschreibt kurz einige der Probleme Interaktion zwischen verwaltetem und nicht verwaltetem Code, und enthält Links zur weiteren Überprüfung kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="92f0b-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="92f0b-117">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="92f0b-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="92f0b-118">Erläutert, Runtime callable Wrapper, kann verwalteten Code COM-Methoden aufrufen und COM callable Wrapper, die COM-Clients zum Aufrufen von Objektmethoden .NET zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="92f0b-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="92f0b-119">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="92f0b-119">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="92f0b-120">Enthält Links zu Themen über COM-Interoperabilität in Bezug auf den Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshallen.</span><span class="sxs-lookup"><span data-stu-id="92f0b-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="92f0b-121">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="92f0b-121">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 <span data-ttu-id="92f0b-122">Erläutert das Tool, das Sie verwenden können, um die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="92f0b-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>

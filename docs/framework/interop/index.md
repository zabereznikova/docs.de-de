---
title: Interoperation mit nicht verwaltetem Code
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f475877bcb7a794d1a58ef9202735e016363678b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="87136-102">Interoperation mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="87136-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="87136-103">.NET Framework stuft die Interaktion mit COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten herauf.</span><span class="sxs-lookup"><span data-stu-id="87136-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="87136-104">Datentypen, Methodensignaturen und Mechanismen zur Behandlung von Fehlern variieren zwischen verwalteten und nicht verwalteten Objektmodellen.</span><span class="sxs-lookup"><span data-stu-id="87136-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="87136-105">Um die Interoperation zwischen .NET Framework-Komponenten und nicht verwaltetem Code sowie den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede in diesen Objektmodellen vor jeweils Clients und Servern.</span><span class="sxs-lookup"><span data-stu-id="87136-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="87136-106">Code, der unter der Kontrolle der Runtime ausgeführt wird, wird als verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="87136-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="87136-107">Umgekehrt wird Code, der außerhalb der Runtime ausgeführt wird, wird als nicht verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="87136-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="87136-108">Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Win32 API-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="87136-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87136-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="87136-109">In This Section</span></span>  
 [<span data-ttu-id="87136-110">Themen zur Vorgehensweise zur Zusammenarbeit mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="87136-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="87136-111">Enthält Links zu allen Themen zur Vorgehensweise in der Begriffsdokumentation zur Interoperabilität mit nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="87136-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="87136-112">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="87136-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="87136-113">Beschreibt, wie COM-Komponenten aus .NET Framework-Anwendungen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="87136-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="87136-114">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="87136-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="87136-115">Beschreibt, wie .NET Framework-Komponenten aus COM-Anwendungen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="87136-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="87136-116">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="87136-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="87136-117">Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="87136-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="87136-118">Entwurfsüberlegungen für die Interoperation</span><span class="sxs-lookup"><span data-stu-id="87136-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="87136-119">Bietet Tipps zum Schreiben integrierter COM-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="87136-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="87136-120">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="87136-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="87136-121">Beschreibt das Marshalling für COM-Interop sowie Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="87136-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="87136-122">Gewusst wie: Zuordnen von HRESULTs und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="87136-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="87136-123">Beschreibt die Zuordnung zwischen Ausnahmen und HRESULTs</span><span class="sxs-lookup"><span data-stu-id="87136-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="87136-124">Interoperation mit generischen Typen</span><span class="sxs-lookup"><span data-stu-id="87136-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="87136-125">Beschreibt das Verhalten generischer Typen bei Verwendung in COM-Interop</span><span class="sxs-lookup"><span data-stu-id="87136-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="87136-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="87136-126">Related Sections</span></span>  
 [<span data-ttu-id="87136-127">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="87136-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="87136-128">Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="87136-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>

---
title: "Verfügbarmachen von COM-Komponenten für .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26efd43a05252e657626063d7dd04b1020dace18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="2e9a6-102">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2e9a6-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="2e9a6-103">In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="2e9a6-104">Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).</span><span class="sxs-lookup"><span data-stu-id="2e9a6-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).</span></span>  
  
 <span data-ttu-id="2e9a6-105">Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="2e9a6-106">Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="2e9a6-107">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2e9a6-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="2e9a6-108">[Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="2e9a6-108">[Import a type library as an assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="2e9a6-109">Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="2e9a6-110">Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="2e9a6-111">[Create COM types in managed Code (Erstellen von COM-Typen in verwaltetem Code)](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span><span class="sxs-lookup"><span data-stu-id="2e9a6-111">[Create COM types in managed Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
     <span data-ttu-id="2e9a6-112">Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="2e9a6-113">[Kompilieren Sie ein Interop-Projekt](../../../docs/framework/interop/compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="2e9a6-113">[Compile an interop project](../../../docs/framework/interop/compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="2e9a6-114">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="2e9a6-115">[Geben Sie eine Interop-Anwendung weiter](../../../docs/framework/interop/deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="2e9a6-115">[Deploy an interop application](../../../docs/framework/interop/deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="2e9a6-116">Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md) im globalen Assemblycache bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e9a6-116">Interop applications are best deployed as [strong-named](../../../docs/framework/app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9a6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e9a6-117">See Also</span></span>  
 [<span data-ttu-id="2e9a6-118">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="2e9a6-118">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="2e9a6-119">Entwurfsüberlegungen für die Interoperation</span><span class="sxs-lookup"><span data-stu-id="2e9a6-119">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [<span data-ttu-id="2e9a6-120">COM-Interop-Beispiel: .NET-Client und COM-Server</span><span class="sxs-lookup"><span data-stu-id="2e9a6-120">COM Interop Sample: .NET Client and COM Server</span></span>](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="2e9a6-121">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="2e9a6-121">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="2e9a6-122">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="2e9a6-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

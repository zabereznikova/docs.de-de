---
title: Verfügbarmachen von COM-Komponenten für .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f644e4f4ff47e31c0f2aaadb577aa6715b445d29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="98ae2-102">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98ae2-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="98ae2-103">In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="98ae2-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="98ae2-104">Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="98ae2-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span></span>
  
 <span data-ttu-id="98ae2-105">Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="98ae2-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="98ae2-106">Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.</span><span class="sxs-lookup"><span data-stu-id="98ae2-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="98ae2-107">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98ae2-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="98ae2-108">[Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="98ae2-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="98ae2-109">Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen.</span><span class="sxs-lookup"><span data-stu-id="98ae2-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="98ae2-110">Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.</span><span class="sxs-lookup"><span data-stu-id="98ae2-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="98ae2-111">[Create COM types in managed Code (Erstellen von COM-Typen in verwaltetem Code)](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="98ae2-111">[Create COM types in managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>  
  
     <span data-ttu-id="98ae2-112">Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="98ae2-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="98ae2-113">[Kompilieren Sie ein Interop-Projekt](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="98ae2-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="98ae2-114">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++.</span><span class="sxs-lookup"><span data-stu-id="98ae2-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="98ae2-115">[Geben Sie eine Interop-Anwendung weiter](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="98ae2-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="98ae2-116">Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../app-domains/strong-named-assemblies.md) im globalen Assemblycache bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="98ae2-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ae2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98ae2-117">See Also</span></span>  
 [<span data-ttu-id="98ae2-118">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="98ae2-118">Interoperating with Unmanaged Code</span></span>](index.md)  
 <span data-ttu-id="98ae2-119">[Entwurfsüberlegungen für die Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="98ae2-119">[Design Considerations for Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100))</span></span>  
 [<span data-ttu-id="98ae2-120">COM-Interop-Beispiel: .NET-Client und COM-Server</span><span class="sxs-lookup"><span data-stu-id="98ae2-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="98ae2-121">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="98ae2-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="98ae2-122">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="98ae2-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)

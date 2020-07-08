---
title: Verfügbarmachen von COM-Komponenten für .NET Framework
description: Lernen Sie den Prozess des Verfügbarmachens von COM-Komponenten für .NET kennen. COM-Komponenten sind in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder isolierte Funktionalität nützlich.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 459ba7ffed2e4f6c458f89a63b2baa37180d270d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620845"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="885bb-104">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="885bb-104">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="885bb-105">In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="885bb-105">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="885bb-106">Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="885bb-106">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="885bb-107">Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="885bb-107">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="885bb-108">Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.</span><span class="sxs-lookup"><span data-stu-id="885bb-108">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="885bb-109">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="885bb-109">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="885bb-110">[Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="885bb-110">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="885bb-111">Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen.</span><span class="sxs-lookup"><span data-stu-id="885bb-111">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="885bb-112">Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.</span><span class="sxs-lookup"><span data-stu-id="885bb-112">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="885bb-113">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) (Verwenden von COM-Typen in verwaltetem Code).</span><span class="sxs-lookup"><span data-stu-id="885bb-113">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="885bb-114">Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="885bb-114">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="885bb-115">[Kompilieren Sie ein Interop-Projekt](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="885bb-115">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="885bb-116">Das Windows SDK bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich Visual Basic, C# und C++.</span><span class="sxs-lookup"><span data-stu-id="885bb-116">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="885bb-117">[Geben Sie eine Interop-Anwendung weiter](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="885bb-117">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="885bb-118">Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../../standard/assembly/strong-named.md) im globalen Assemblycache bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="885bb-118">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885bb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="885bb-119">See also</span></span>

- [<span data-ttu-id="885bb-120">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="885bb-120">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="885bb-121">[Entwurfsüberlegungen für die Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="885bb-121">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="885bb-122">COM-Interop-Beispiel: .NET-Client und COM-Server</span><span class="sxs-lookup"><span data-stu-id="885bb-122">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="885bb-123">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="885bb-123">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="885bb-124">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="885bb-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)

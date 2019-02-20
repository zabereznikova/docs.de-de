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
ms.openlocfilehash: 6987dea6f122819b9f1c0d334440d87545368942
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220106"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="60296-102">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="60296-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="60296-103">In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="60296-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="60296-104">Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="60296-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="60296-105">Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="60296-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="60296-106">Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.</span><span class="sxs-lookup"><span data-stu-id="60296-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="60296-107">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="60296-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="60296-108">[Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="60296-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="60296-109">Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen.</span><span class="sxs-lookup"><span data-stu-id="60296-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="60296-110">Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.</span><span class="sxs-lookup"><span data-stu-id="60296-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="60296-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) (Verwenden von COM-Typen in verwaltetem Code).</span><span class="sxs-lookup"><span data-stu-id="60296-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="60296-112">Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="60296-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="60296-113">[Kompilieren Sie ein Interop-Projekt](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="60296-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="60296-114">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++.</span><span class="sxs-lookup"><span data-stu-id="60296-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="60296-115">[Geben Sie eine Interop-Anwendung weiter](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="60296-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="60296-116">Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../app-domains/strong-named-assemblies.md) im globalen Assemblycache bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="60296-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60296-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60296-117">See also</span></span>
- [<span data-ttu-id="60296-118">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="60296-118">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="60296-119">[Entwurfsüberlegungen für die Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60296-119">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="60296-120">COM-Interop-Beispiel: .NET-Client und COM-Server</span><span class="sxs-lookup"><span data-stu-id="60296-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="60296-121">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="60296-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="60296-122">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="60296-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)

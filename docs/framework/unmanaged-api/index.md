---
title: Referenz zur nicht verwalteten API
ms.date: 11/06/2017
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd84d84706a0d61f26b576b7300fae87fbe602e8
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303392"
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="cdf2f-102">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="cdf2f-102">Unmanaged API Reference</span></span>
<span data-ttu-id="cdf2f-103">Dieser Abschnitt enthält Informationen zu nicht verwalteten APIs, die von Anwendungen mit verwaltetem Code verwendet werden können, wie Laufzeithosts, Compiler, Disassembler, Obfuskatoren, Debugger und Profiler.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdf2f-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cdf2f-104">In This Section</span></span>  
 [<span data-ttu-id="cdf2f-105">Allgemeine Datentypen</span><span class="sxs-lookup"><span data-stu-id="cdf2f-105">Common Data Types</span></span>](../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="cdf2f-106">Führt häufig verwendete Datentypen auf, im Besonderen für unverwaltete Profilerstellungs- und Debug-APIs.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="cdf2f-107">ALink</span><span class="sxs-lookup"><span data-stu-id="cdf2f-107">ALink</span></span>](../../../docs/framework/unmanaged-api/alink/index.md)  
 <span data-ttu-id="cdf2f-108">Beschreibt die ALink-API, die die Erstellung von .NET Framework-Assemblys und ungebundenen Modulen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="cdf2f-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="cdf2f-109">Authenticode</span></span>](../../../docs/framework/unmanaged-api/authenticode/index.md)  
 <span data-ttu-id="cdf2f-110">Unterstützt das Authenticode XrML-Lizenterstellungs- und Überprüfungsmodul.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="cdf2f-111">Konstanten</span><span class="sxs-lookup"><span data-stu-id="cdf2f-111">Constants</span></span>](../../../docs/framework/unmanaged-api/constants-unmanaged-api-reference.md)  
 <span data-ttu-id="cdf2f-112">Beschreibt die Konstanten, die in CorSym.idl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 <span data-ttu-id="cdf2f-113">[Benutzerdefinierte Schnittstellenattribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cdf2f-113">[Custom Interface Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span></span>  
 <span data-ttu-id="cdf2f-114">Beschreibt benutzerdefinierte Schnittstellenattribute des Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="cdf2f-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="cdf2f-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cdf2f-115">Debugging</span></span>](../../../docs/framework/unmanaged-api/debugging/index.md)  
 <span data-ttu-id="cdf2f-116">Beschreibt die Debug-API, die es dem Debugger ermöglicht, Code zu debuggen, der in der CLR-Umgebung (Common Language Runtime) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="cdf2f-117">Diagnosesymbolspeicher</span><span class="sxs-lookup"><span data-stu-id="cdf2f-117">Diagnostics Symbol Store</span></span>](../../../docs/framework/unmanaged-api/diagnostics/index.md)  
 <span data-ttu-id="cdf2f-118">Beschreibt die Diagnosesymbolspeicher-API, mit der ein Compiler Symbolinformationen generieren kann, die von einem Debugger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="cdf2f-119">Fusion</span><span class="sxs-lookup"><span data-stu-id="cdf2f-119">Fusion</span></span>](../../../docs/framework/unmanaged-api/fusion/index.md)  
 <span data-ttu-id="cdf2f-120">Beschreibt die Fusion-API, über die ein Laufzeithost auf die Eigenschaften der Ressourcen einer Anwendung zugreifen kann, um die richtigen Versionen dieser Ressourcen für die Anwendung zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="cdf2f-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="cdf2f-121">Hosting</span></span>](../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="cdf2f-122">Beschreibt die Hosting-API, die nicht verwaltete Hosts aktiviert, um die CLR in ihre Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="cdf2f-123">Metadaten</span><span class="sxs-lookup"><span data-stu-id="cdf2f-123">Metadata</span></span>](../../../docs/framework/unmanaged-api/metadata/index.md)  
 <span data-ttu-id="cdf2f-124">Beschreibt die Metadaten-API, die einem Client (z. B. einem Compiler) die Generierung oder den Zugriff auf Komponentenmetadaten ermöglicht, ohne dass die Typen von der Common Language Runtime (CLR) geladen werden.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="cdf2f-125">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="cdf2f-125">Profiling</span></span>](../../../docs/framework/unmanaged-api/profiling/index.md)  
 <span data-ttu-id="cdf2f-126">Beschreibt die Profilerstellungs-API, die es einem Profiler ermöglicht, die Ausführung eines Programms durch die Common Language Runtime (CLR) zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="cdf2f-127">Starke Namen</span><span class="sxs-lookup"><span data-stu-id="cdf2f-127">Strong Naming</span></span>](../../../docs/framework/unmanaged-api/strong-naming/index.md)  
 <span data-ttu-id="cdf2f-128">Beschreibt die API für starke Namen, die einem Client ermöglicht, die starke Namenssignierung für Assemblys zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="cdf2f-129">WMI und Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="cdf2f-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="cdf2f-130">Beschreibt die APIs, die Aufrufe an Bibliotheken der Windows-Verwaltungsinstrumentation (WMI) umschließen.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="cdf2f-131">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="cdf2f-131">Tlbexp Helper Functions</span></span>](../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="cdf2f-132">Beschreibt die beiden Hilfsfunktionen und eine Schnittstelle, die vom Typbibliothekexporter (Tlbexp.exe) bei der Konvertierung von Assemblys in Typbibliotheken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdf2f-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cdf2f-133">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cdf2f-133">Related Sections</span></span>  
 [<span data-ttu-id="cdf2f-134">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="cdf2f-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  

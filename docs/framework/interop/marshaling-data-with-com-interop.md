---
title: Marshallen von Daten mit COM-Interop
description: Weitere Informationen finden Sie in den Artikeln zum Marshallen von Daten mit COM-Interop. Die Tools „Tlbimp.exe“ und „Tlbexp.exe“ dienen zum Konvertieren zwischen einer COM-Typbibliothek und einer Interopassembly.
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: bcbd2c50fcbd9af3f2eead57ac2e26f8db0c6ad6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275943"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="40469-104">Marshallen von Daten mit COM-Interop</span><span class="sxs-lookup"><span data-stu-id="40469-104">Marshaling Data with COM Interop</span></span>

<span data-ttu-id="40469-105">COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM.</span><span class="sxs-lookup"><span data-stu-id="40469-105">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="40469-106">Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.</span><span class="sxs-lookup"><span data-stu-id="40469-106">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="40469-107">Das Windows SDK umfasst die folgenden COM-Interop-Tools:</span><span class="sxs-lookup"><span data-stu-id="40469-107">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="40469-108">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert.</span><span class="sxs-lookup"><span data-stu-id="40469-108">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="40469-109">Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="40469-109">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="40469-110">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.</span><span class="sxs-lookup"><span data-stu-id="40469-110">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="40469-111">Die folgenden Abschnitte verweisen auf Themen, in denen die Prozesse zum Anpassen von Interop-Wrappern beschrieben werden, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).</span><span class="sxs-lookup"><span data-stu-id="40469-111">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40469-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="40469-112">In This Section</span></span>  

<span data-ttu-id="40469-113">[How to: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md): Beschreibt, wie Sie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="40469-113">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Describes how to create a COM wrapper manually in managed source code.</span></span>

 [<span data-ttu-id="40469-114">How to: Migrieren von verwaltetem Code DCOM zu WCF</span><span class="sxs-lookup"><span data-stu-id="40469-114">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="40469-115">Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.</span><span class="sxs-lookup"><span data-stu-id="40469-115">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="40469-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="40469-116">Related Sections</span></span>  

 <span data-ttu-id="40469-117">[COM-Datentypen](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-117">[COM Data Types](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="40469-118">Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.</span><span class="sxs-lookup"><span data-stu-id="40469-118">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="40469-119">[Anpassen von COM-Aufrufwrappern](/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-119">[Customizing COM Callable Wrappers](/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="40469-120">Beschreibt, wie Sie Datentypen mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs zur Entwurfszeit explizit marshallen.</span><span class="sxs-lookup"><span data-stu-id="40469-120">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="40469-121">[Anpassen von Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-121">[Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="40469-122">Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="40469-122">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="40469-123">[Erweiterte COM-Interoperabilität](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-123">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="40469-124">Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="40469-124">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="40469-125">[Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-125">[Assembly to Type Library Conversion Summary](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="40469-126">Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="40469-126">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="40469-127">[Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-127">[Type Library to Assembly Conversion Summary](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="40469-128">Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="40469-128">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="40469-129">[Interoperation mit generischen Typen](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40469-129">[Interoperating Using Generic Types](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="40469-130">Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="40469-130">Describes which actions are supported when using generic types for COM interoperability.</span></span>

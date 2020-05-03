---
title: Marshallen von Daten mit COM-Interop
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: ae41713d5349321725599c0c38d7c6fc515c374b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181370"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="c760e-102">Marshallen von Daten mit COM-Interop</span><span class="sxs-lookup"><span data-stu-id="c760e-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="c760e-103">COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM.</span><span class="sxs-lookup"><span data-stu-id="c760e-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="c760e-104">Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.</span><span class="sxs-lookup"><span data-stu-id="c760e-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="c760e-105">Das Windows SDK umfasst die folgenden COM-Interop-Tools:</span><span class="sxs-lookup"><span data-stu-id="c760e-105">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="c760e-106">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c760e-106">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="c760e-107">Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="c760e-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="c760e-108">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.</span><span class="sxs-lookup"><span data-stu-id="c760e-108">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="c760e-109">Die folgenden Abschnitte verweisen auf Themen, in denen die Prozesse zum Anpassen von Interop-Wrappern beschrieben werden, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).</span><span class="sxs-lookup"><span data-stu-id="c760e-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c760e-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c760e-110">In This Section</span></span>  
<span data-ttu-id="c760e-111">[How to: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md): Beschreibt, wie Sie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="c760e-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Describes how to create a COM wrapper manually in managed source code.</span></span>

 [<span data-ttu-id="c760e-112">How to: Migrieren von verwaltetem Code DCOM zu WCF</span><span class="sxs-lookup"><span data-stu-id="c760e-112">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="c760e-113">Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.</span><span class="sxs-lookup"><span data-stu-id="c760e-113">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c760e-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c760e-114">Related Sections</span></span>  
 <span data-ttu-id="c760e-115">[COM-Datentypen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-115">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-116">Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.</span><span class="sxs-lookup"><span data-stu-id="c760e-116">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="c760e-117">[Anpassen von COM-Aufrufwrappern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-117">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-118">Beschreibt, wie Sie Datentypen mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs zur Entwurfszeit explizit marshallen.</span><span class="sxs-lookup"><span data-stu-id="c760e-118">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="c760e-119">[Anpassen von Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-119">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-120">Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c760e-120">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="c760e-121">[Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-121">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-122">Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="c760e-122">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="c760e-123">[Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-123">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-124">Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c760e-124">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="c760e-125">[Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-125">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-126">Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="c760e-126">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="c760e-127">[Interoperation mit generischen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c760e-127">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="c760e-128">Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c760e-128">Describes which actions are supported when using generic types for COM interoperability.</span></span>

---
title: Marshallen von Daten mit COM-Interop
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16f94e8b85a1bedb8b7791c2b7fcaf6d154ba1b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833523"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="03703-102">Marshallen von Daten mit COM-Interop</span><span class="sxs-lookup"><span data-stu-id="03703-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="03703-103">COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM.</span><span class="sxs-lookup"><span data-stu-id="03703-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="03703-104">Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.</span><span class="sxs-lookup"><span data-stu-id="03703-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="03703-105">Das Windows Software Development Kit (SDK) enthält die folgenden COM-Interop-Tools:</span><span class="sxs-lookup"><span data-stu-id="03703-105">The Windows Software Development Kit (SDK) includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="03703-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert.</span><span class="sxs-lookup"><span data-stu-id="03703-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="03703-107">Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="03703-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="03703-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.</span><span class="sxs-lookup"><span data-stu-id="03703-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="03703-109">Die folgenden Abschnitte verweisen auf Themen, in denen die Prozesse zum Anpassen von Interop-Wrappern beschrieben werden, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).</span><span class="sxs-lookup"><span data-stu-id="03703-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03703-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="03703-110">In This Section</span></span>  
<span data-ttu-id="03703-111">[Vorgehensweise: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="03703-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="03703-112">Beschreibt, wie Sie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="03703-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="03703-113">Vorgehensweise: Migrieren von verwaltetem Code DCOM zu WCF</span><span class="sxs-lookup"><span data-stu-id="03703-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="03703-114">Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.</span><span class="sxs-lookup"><span data-stu-id="03703-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="03703-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="03703-115">Related Sections</span></span>  
 <span data-ttu-id="03703-116">[COM-Datentypen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-116">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="03703-117">Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.</span><span class="sxs-lookup"><span data-stu-id="03703-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="03703-118">[Anpassen von COM-Aufrufwrappern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-118">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="03703-119">Beschreibt, wie Sie Datentypen mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs zur Entwurfszeit explizit marshallen.</span><span class="sxs-lookup"><span data-stu-id="03703-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="03703-120">[Anpassen von Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-120">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="03703-121">Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="03703-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="03703-122">[Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-122">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="03703-123">Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="03703-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="03703-124">[Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-124">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="03703-125">Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="03703-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="03703-126">[Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-126">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="03703-127">Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="03703-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="03703-128">[Interoperation mit generischen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03703-128">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="03703-129">Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="03703-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>

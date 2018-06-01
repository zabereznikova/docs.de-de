---
title: Marshallen von Daten mit COM-Interop
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0d94223223568efe921af3a340815a966cc6c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388354"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="d5351-102">Marshallen von Daten mit COM-Interop</span><span class="sxs-lookup"><span data-stu-id="d5351-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="d5351-103">COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM.</span><span class="sxs-lookup"><span data-stu-id="d5351-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="d5351-104">Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.</span><span class="sxs-lookup"><span data-stu-id="d5351-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="d5351-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] umfasst die folgenden COM-Interop-Tools:</span><span class="sxs-lookup"><span data-stu-id="d5351-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="d5351-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d5351-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="d5351-107">Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5351-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="d5351-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.</span><span class="sxs-lookup"><span data-stu-id="d5351-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="d5351-109">Die folgenden Abschnitte verweisen auf Themen, in denen die Prozesse zum Anpassen von Interop-Wrappern beschrieben werden, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).</span><span class="sxs-lookup"><span data-stu-id="d5351-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5351-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5351-110">In This Section</span></span>  
<span data-ttu-id="d5351-111">[Vorgehensweise: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="d5351-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="d5351-112">Beschreibt, wie Sie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5351-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="d5351-113">How to: Migrate Managed-Code DCOM to WCF (Vorgehensweise: Migrieren von verwaltetem Code DCOM zu WCF)</span><span class="sxs-lookup"><span data-stu-id="d5351-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="d5351-114">Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.</span><span class="sxs-lookup"><span data-stu-id="d5351-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5351-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d5351-115">Related Sections</span></span>  
 <span data-ttu-id="d5351-116">[COM-Datentypen](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-116">[COM Data Types](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-117">Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.</span><span class="sxs-lookup"><span data-stu-id="d5351-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="d5351-118">[Anpassen von COM-Aufrufwrappern](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-119">Beschreibt, wie Sie Datentypen mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs zur Entwurfszeit explizit marshallen.</span><span class="sxs-lookup"><span data-stu-id="d5351-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="d5351-120">[Anpassen von Runtime Callable Wrappers](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-121">Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d5351-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="d5351-122">[Erweiterte COM-Interoperabilität](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-122">[Advanced COM Interoperability](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-123">Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="d5351-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="d5351-124">[Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-125">Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="d5351-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="d5351-126">[Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-127">Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="d5351-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="d5351-128">[Interoperation mit generischen Typen](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5351-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="d5351-129">Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d5351-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>

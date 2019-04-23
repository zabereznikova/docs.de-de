---
title: Verpacken einer Assembly für COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc02178223e48c7c578d10ba92123d9436d4f439
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097264"
---
# <a name="packaging-an-assembly-for-com"></a><span data-ttu-id="fb39e-102">Verpacken einer Assembly für COM</span><span class="sxs-lookup"><span data-stu-id="fb39e-102">Packaging an Assembly for COM</span></span>
<span data-ttu-id="fb39e-103">COM-Entwickler profitieren von den folgenden Informationen zu den verwalteten Typen, die sie in ihre Anwendung integrieren möchten:</span><span class="sxs-lookup"><span data-stu-id="fb39e-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>  
  
-   <span data-ttu-id="fb39e-104">Eine Liste von Typen, die COM-Anwendungen nutzen können</span><span class="sxs-lookup"><span data-stu-id="fb39e-104">A list of types that COM applications can consume</span></span>  
  
     <span data-ttu-id="fb39e-105">Einige verwalteten Typen sind nicht für COM sichtbar; einige sind sichtbar, aber nicht erstellbar, und andere sind sichtbar und erstellbar.</span><span class="sxs-lookup"><span data-stu-id="fb39e-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="fb39e-106">Eine Assembly kann eine beliebige Kombination von nicht sichtbaren, sichtbaren, nicht erstellbaren und erstellbaren Typen umfassen.</span><span class="sxs-lookup"><span data-stu-id="fb39e-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="fb39e-107">Aus Gründen der Vollständigkeit identifizieren Sie die Typen in einer Assembly, die für COM verfügbar gemacht werden sollen, insbesondere, wenn diese Typen eine Teilmenge der Typen sind, die für .NET Framework verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb39e-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>  
  
     <span data-ttu-id="fb39e-108">Weitere Informationen finden Sie unter [Qualifizieren von .NET-Typen für die Interoperation](qualifying-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="fb39e-108">For additional information, see [Qualifying .NET Types for Interoperation](qualifying-net-types-for-interoperation.md).</span></span>  
  
-   <span data-ttu-id="fb39e-109">Anweisungen der Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fb39e-109">Versioning instructions</span></span>  
  
     <span data-ttu-id="fb39e-110">Verwaltete Klassen, die die Klassenschnittstelle (eine von COM-Interop generierte Schnittstelle) implementieren, unterliegen Einschränkungen der Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="fb39e-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>  
  
     <span data-ttu-id="fb39e-111">Richtlinien zur Verwendung der Klassenschnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="fb39e-111">For guidelines on using the class interface, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
-   <span data-ttu-id="fb39e-112">Anweisungen zur Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="fb39e-112">Deployment instructions</span></span>  
  
     <span data-ttu-id="fb39e-113">Assemblys mit starken Namen, die von einem Herausgeber signiert wurden, können im globalen Assemblycache installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb39e-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="fb39e-114">Nicht signierte Assemblys müssen als private Assemblys auf dem Computer des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb39e-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>  
  
     <span data-ttu-id="fb39e-115">Weitere Informationen finden Sie unter [Überlegungen zur Assemblysicherheit](../app-domains/assembly-security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="fb39e-115">For additional information, see [Assembly Security Considerations](../app-domains/assembly-security-considerations.md).</span></span>  
  
-   <span data-ttu-id="fb39e-116">Einbindung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="fb39e-116">Type library inclusion</span></span>  
  
     <span data-ttu-id="fb39e-117">Die meisten Typen erfordern eine Typbibliothek, wenn sie von einer COM-Anwendung genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="fb39e-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="fb39e-118">Sie können eine Typbibliothek generieren oder COM-Entwickler mit der Ausführung dieser Aufgabe betreuen.</span><span class="sxs-lookup"><span data-stu-id="fb39e-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="fb39e-119">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet die folgenden Optionen zum Generieren einer Typbibliothek:</span><span class="sxs-lookup"><span data-stu-id="fb39e-119">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides the following options for generating a type library:</span></span>  
  
    -   [<span data-ttu-id="fb39e-120">Type Library Exporter-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)  
  
    -   [<span data-ttu-id="fb39e-121">TypeLibConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="fb39e-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)  
  
    -   [<span data-ttu-id="fb39e-122">Assembly Registration-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)  
  
    -   [<span data-ttu-id="fb39e-123">.NET Services Installation-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)  
  
     <span data-ttu-id="fb39e-124">Unabhängig vom Mechanismus, den Sie auswählen, sind nur öffentliche Typen in der von Ihnen bereitgestellten Assembly in der generierten Typbibliothek enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb39e-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>  
  
     <span data-ttu-id="fb39e-125">Sie können eine Typbibliothek als separate Datei verpacken oder sie als Win32-Ressourcendatei in eine .NET-basierte Anwendung einbetten.</span><span class="sxs-lookup"><span data-stu-id="fb39e-125">You can package a type library as a separate file or embed it as Win32 resource file within a .NET-based application.</span></span> <span data-ttu-id="fb39e-126">Microsoft Visual Basic 6.0 führt diese Aufgabe automatisch für Sie aus. Bei der Verwendung von [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] müssen Sie die Typbibliothek jedoch manuell einbetten.</span><span class="sxs-lookup"><span data-stu-id="fb39e-126">Microsoft Visual Basic 6.0 performed this task for you automatically; however, when using [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)], you must embed your type library manually.</span></span> <span data-ttu-id="fb39e-127">Anweisungen hierzu finden Sie unter [Vorgehensweise: Einbetten von Typbibliotheken als Win32-Ressourcen in .NET-Anwendungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fb39e-127">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## <a name="type-library-exporter"></a><span data-ttu-id="fb39e-128">Type Library Exporter-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-128">Type Library Exporter</span></span>  
 <span data-ttu-id="fb39e-129">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) ist ein Befehlszeilentool, das die in einer Assembly enthaltenen Klassen und Schnittstellen in eine COM-Typbibliothek konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fb39e-129">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="fb39e-130">Sobald die Typinformationen der Klasse verfügbar sind, können COM-Clients eine Instanz der .NET-Klasse erstellen und die Methoden der Instanz aufrufen, als ob es sich um ein COM-Objekt handeln würde.</span><span class="sxs-lookup"><span data-stu-id="fb39e-130">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="fb39e-131">Tlbexp.exe konvertiert eine ganze Assembly gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="fb39e-131">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="fb39e-132">Sie können mit Tlbexp.exekeine Typinformationen für einen Teil der in der Assembly definierten Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="fb39e-132">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## <a name="typelibconverter-class"></a><span data-ttu-id="fb39e-133">TypeLibConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="fb39e-133">TypeLibConverter Class</span></span>  
 <span data-ttu-id="fb39e-134">Die <xref:System.Runtime.InteropServices.TypeLibConverter>-Klasse im **System.Runtime.Interop**-Namespace konvertiert die Klassen und Schnittstellen, die in einer Assembly enthalten sind, in eine COM-Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb39e-134">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="fb39e-135">Diese API erzeugt dieselben Typinformationen wie das Type Library Exporter-Tool, das im vorherigen Abschnitt beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="fb39e-135">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>  
  
 <span data-ttu-id="fb39e-136">Die **TypeLibConverter-Klasse** implementiert die <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="fb39e-136">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## <a name="assembly-registration-tool"></a><span data-ttu-id="fb39e-137">Assembly Registration-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-137">Assembly Registration Tool</span></span>  
 <span data-ttu-id="fb39e-138">Das [Assembly Registration-Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) kann eine Typbibliothek beim Anwenden der **/tlb:**-Option generieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="fb39e-138">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="fb39e-139">COM-Clients erfordern, dass Typbibliotheken in der Windows-Registrierung installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb39e-139">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="fb39e-140">Ohne diese Option registriert Regasm.exe nur die Typen in einer Assembly, nicht die Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb39e-140">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="fb39e-141">Die Registrierung der Typen in einer Assembly, und die Registrierung der Typbibliothek sind verschiedene Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="fb39e-141">Registering the types in an assembly and registering the type library are distinct activities.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## <a name="net-services-installation-tool"></a><span data-ttu-id="fb39e-142">.NET Services Installation-Tool</span><span class="sxs-lookup"><span data-stu-id="fb39e-142">.NET Services Installation Tool</span></span>  
 <span data-ttu-id="fb39e-143">Das [.NET Services Installation-Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) fügt verwaltete Klassen zu Windows 2000-Komponentendiensten hinzu, kombiniert mehrere Aufgaben innerhalb eines einzigen Tools.</span><span class="sxs-lookup"><span data-stu-id="fb39e-143">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="fb39e-144">Zusätzlich zum Laden und Registrieren der Assembly, generiert, registriert und installiert Regsvcs.exe die Typbibliothek in eine vorhandene COM+ 1.0-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fb39e-144">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb39e-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb39e-145">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="fb39e-146">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="fb39e-146">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="fb39e-147">Qualifizieren von .NET-Typen für die Interoperation</span><span class="sxs-lookup"><span data-stu-id="fb39e-147">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)
- [<span data-ttu-id="fb39e-148">Einführung in die Klassenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb39e-148">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="fb39e-149">Überlegungen zur Assemblysicherheit</span><span class="sxs-lookup"><span data-stu-id="fb39e-149">Assembly Security Considerations</span></span>](../app-domains/assembly-security-considerations.md)
- [<span data-ttu-id="fb39e-150">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="fb39e-150">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="fb39e-151">Registrieren von Assemblys mit COM</span><span class="sxs-lookup"><span data-stu-id="fb39e-151">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- [<span data-ttu-id="fb39e-152">Vorgehensweise: Einbetten von Typbibliotheken als Win32-Ressourcen in .NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="fb39e-152">How to: Embed Type Libraries as Win32 Resources in Applications</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))

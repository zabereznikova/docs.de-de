---
title: Packen einer .NET Framework-Assembly für COM
description: Packen Sie eine .NET-Assembly für COM. Erstellen Sie die Liste der Typen, die COM-Anwendungen nutzen können. Erfahren Sie zudem mehr zur Versionsverwaltung, zu Bereitstellungsanweisungen und zur Typbibliothek.
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
ms.openlocfilehash: 5fde7f7f00aadf4d941d4ffe522453970b67e9e2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554129"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a><span data-ttu-id="93312-104">Packen einer .NET Framework-Assembly für COM</span><span class="sxs-lookup"><span data-stu-id="93312-104">Packaging a .NET Framework Assembly for COM</span></span>

<span data-ttu-id="93312-105">COM-Entwickler profitieren von den folgenden Informationen zu den verwalteten Typen, die sie in ihre Anwendung integrieren möchten:</span><span class="sxs-lookup"><span data-stu-id="93312-105">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="93312-106">Eine Liste von Typen, die COM-Anwendungen nutzen können</span><span class="sxs-lookup"><span data-stu-id="93312-106">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="93312-107">Einige verwalteten Typen sind nicht für COM sichtbar; einige sind sichtbar, aber nicht erstellbar, und andere sind sichtbar und erstellbar.</span><span class="sxs-lookup"><span data-stu-id="93312-107">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="93312-108">Eine Assembly kann eine beliebige Kombination von nicht sichtbaren, sichtbaren, nicht erstellbaren und erstellbaren Typen umfassen.</span><span class="sxs-lookup"><span data-stu-id="93312-108">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="93312-109">Aus Gründen der Vollständigkeit identifizieren Sie die Typen in einer Assembly, die für COM verfügbar gemacht werden sollen, insbesondere, wenn diese Typen eine Teilmenge der Typen sind, die für .NET Framework verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="93312-109">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="93312-110">Weitere Informationen finden Sie unter [Qualifizieren von .NET-Typen für die Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="93312-110">For additional information, see [Qualifying .NET Types for Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="93312-111">Anweisungen der Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="93312-111">Versioning instructions</span></span>

  <span data-ttu-id="93312-112">Verwaltete Klassen, die die Klassenschnittstelle (eine von COM-Interop generierte Schnittstelle) implementieren, unterliegen Einschränkungen der Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="93312-112">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="93312-113">Richtlinien zur Verwendung der Klassenschnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="93312-113">For guidelines on using the class interface, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="93312-114">Anweisungen zur Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="93312-114">Deployment instructions</span></span>

  <span data-ttu-id="93312-115">Assemblys mit starken Namen, die von einem Herausgeber signiert wurden, können im globalen Assemblycache installiert werden.</span><span class="sxs-lookup"><span data-stu-id="93312-115">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="93312-116">Nicht signierte Assemblys müssen als private Assemblys auf dem Computer des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="93312-116">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="93312-117">Weitere Informationen finden Sie unter [Überlegungen zur Assemblysicherheit](../../standard/assembly/security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="93312-117">For additional information, see [Assembly Security Considerations](../../standard/assembly/security-considerations.md).</span></span>

- <span data-ttu-id="93312-118">Einbindung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="93312-118">Type library inclusion</span></span>

  <span data-ttu-id="93312-119">Die meisten Typen erfordern eine Typbibliothek, wenn sie von einer COM-Anwendung genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="93312-119">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="93312-120">Sie können eine Typbibliothek generieren oder COM-Entwickler mit der Ausführung dieser Aufgabe betreuen.</span><span class="sxs-lookup"><span data-stu-id="93312-120">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="93312-121">Das Windows SDK bietet die folgenden Optionen zum Generieren einer Typbibliothek:</span><span class="sxs-lookup"><span data-stu-id="93312-121">The Windows SDK provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="93312-122">Type Library Exporter-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-122">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="93312-123">TypeLibConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="93312-123">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="93312-124">Assembly Registration-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-124">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="93312-125">.NET Services Installation-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-125">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="93312-126">Unabhängig vom Mechanismus, den Sie auswählen, sind nur öffentliche Typen in der von Ihnen bereitgestellten Assembly in der generierten Typbibliothek enthalten.</span><span class="sxs-lookup"><span data-stu-id="93312-126">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

<span data-ttu-id="93312-127">Anweisungen hierzu finden Sie unter [Vorgehensweise: Einbetten von Typbibliotheken als Win32-Ressourcen in .NET-Anwendungen](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="93312-127">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="93312-128">Type Library Exporter-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-128">Type Library Exporter</span></span>

<span data-ttu-id="93312-129">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) ist ein Befehlszeilentool, das die in einer Assembly enthaltenen Klassen und Schnittstellen in eine COM-Typbibliothek konvertiert.</span><span class="sxs-lookup"><span data-stu-id="93312-129">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="93312-130">Sobald die Typinformationen der Klasse verfügbar sind, können COM-Clients eine Instanz der .NET-Klasse erstellen und die Methoden der Instanz aufrufen, als ob es sich um ein COM-Objekt handeln würde.</span><span class="sxs-lookup"><span data-stu-id="93312-130">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="93312-131">Tlbexp.exe konvertiert eine ganze Assembly gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="93312-131">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="93312-132">Sie können mit Tlbexp.exekeine Typinformationen für einen Teil der in der Assembly definierten Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="93312-132">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="93312-133">TypeLibConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="93312-133">TypeLibConverter Class</span></span>

<span data-ttu-id="93312-134">Die <xref:System.Runtime.InteropServices.TypeLibConverter>-Klasse im **System.Runtime.Interop**-Namespace konvertiert die Klassen und Schnittstellen, die in einer Assembly enthalten sind, in eine COM-Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="93312-134">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="93312-135">Diese API erzeugt dieselben Typinformationen wie das Type Library Exporter-Tool, das im vorherigen Abschnitt beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="93312-135">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="93312-136">Die **TypeLibConverter-Klasse** implementiert die <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="93312-136">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="93312-137">Assembly Registration-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-137">Assembly Registration Tool</span></span>

<span data-ttu-id="93312-138">Das [Assembly Registration-Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) kann eine Typbibliothek beim Anwenden der **/tlb:** -Option generieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="93312-138">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="93312-139">COM-Clients erfordern, dass Typbibliotheken in der Windows-Registrierung installiert werden.</span><span class="sxs-lookup"><span data-stu-id="93312-139">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="93312-140">Ohne diese Option registriert Regasm.exe nur die Typen in einer Assembly, nicht die Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="93312-140">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="93312-141">Die Registrierung der Typen in einer Assembly, und die Registrierung der Typbibliothek sind verschiedene Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="93312-141">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="93312-142">.NET Services Installation-Tool</span><span class="sxs-lookup"><span data-stu-id="93312-142">.NET Services Installation Tool</span></span>

<span data-ttu-id="93312-143">Das [.NET Services Installation-Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) fügt verwaltete Klassen zu Windows 2000-Komponentendiensten hinzu, kombiniert mehrere Aufgaben innerhalb eines einzigen Tools.</span><span class="sxs-lookup"><span data-stu-id="93312-143">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="93312-144">Zusätzlich zum Laden und Registrieren der Assembly, generiert, registriert und installiert Regsvcs.exe die Typbibliothek in eine vorhandene COM+ 1.0-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="93312-144">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="93312-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93312-145">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="93312-146">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="93312-146">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="93312-147">Qualifizieren von .NET-Typen für die Interoperation</span><span class="sxs-lookup"><span data-stu-id="93312-147">Qualifying .NET Types for Interoperation</span></span>](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="93312-148">Einführung in die Klassenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="93312-148">Introducing the class interface</span></span>](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="93312-149">Überlegungen zur Assemblysicherheit</span><span class="sxs-lookup"><span data-stu-id="93312-149">Assembly Security Considerations</span></span>](../../standard/assembly/security-considerations.md)
- [<span data-ttu-id="93312-150">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="93312-150">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="93312-151">Registrieren von Assemblys bei COM</span><span class="sxs-lookup"><span data-stu-id="93312-151">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="93312-152">[How to: Einbetten von Typbibliotheken als Win32-Ressourcen in .NET-Anwendungen](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="93312-152">[How to: Embed Type Libraries as Win32 Resources in Applications](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>

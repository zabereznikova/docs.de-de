---
title: Programmieren mit Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6a20a2e678c10157fed7da6f5de9f3ffee0c9ad
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751869"
---
# <a name="programming-with-assemblies"></a><span data-ttu-id="be360-102">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="be360-102">Programming with Assemblies</span></span>
<span data-ttu-id="be360-103">Assemblys sind die Bausteine von .NET Framework; sie bilden das Fundament für Bereitstellung, Versionskontrolle, Wiederverwendung, Gültigkeitsbereiche für die Aktivierung und Sicherheitsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="be360-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="be360-104">Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="be360-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="be360-105">Sie ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden.</span><span class="sxs-lookup"><span data-stu-id="be360-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="be360-106">Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.</span><span class="sxs-lookup"><span data-stu-id="be360-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="be360-107">In diesem Abschnitt wird beschrieben, wie Module, Assembys aus Modulen und ein Schlüsselpaar erstellt werden, wie eine Assembly mit einem starken Namen signiert wird und wie eine Assembly im globalen Assemblycache installiert wird.</span><span class="sxs-lookup"><span data-stu-id="be360-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="be360-108">Dieser Abschnitt beschreibt zusätzlich, wie Sie [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Informationen aus dem Assemblymanifest anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="be360-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be360-109">Ab der .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladenen Runtime besitzt.</span><span class="sxs-lookup"><span data-stu-id="be360-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="be360-110">Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="be360-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be360-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="be360-111">In This Section</span></span>  
 [<span data-ttu-id="be360-112">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="be360-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="be360-113">Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.</span><span class="sxs-lookup"><span data-stu-id="be360-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="be360-114">Assemblynamen</span><span class="sxs-lookup"><span data-stu-id="be360-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="be360-115">Bietet eine Übersicht über die Assemblybenennung.</span><span class="sxs-lookup"><span data-stu-id="be360-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="be360-116">Gewusst wie: Bestimmen des vollqualifizierten Namens einer Assembly</span><span class="sxs-lookup"><span data-stu-id="be360-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="be360-117">Beschreibt, wie der vollqualifizierte Namen einer Assembly bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="be360-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="be360-118">Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="be360-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="be360-119">Beschreibt, wie Legacysicherheitsrichtlinien für voll vertrauenswürdige Assemblys in einer Intranetfreigabe angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be360-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="be360-120">Assemblyspeicherort</span><span class="sxs-lookup"><span data-stu-id="be360-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="be360-121">Bietet eine Übersicht, wo Assemblys zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="be360-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="be360-122">Gewusst wie: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="be360-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="be360-123">Beschreibt das Erstellen einer Assembly mit einer einzigen Datei.</span><span class="sxs-lookup"><span data-stu-id="be360-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="be360-124">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="be360-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="be360-125">Beschreibt Gründe für das Erstellen von Assemblys mit mehreren Dateien.</span><span class="sxs-lookup"><span data-stu-id="be360-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="be360-126">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="be360-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="be360-127">Beschreibt das Erstellen einer Assembly mit mehreren Dateien.</span><span class="sxs-lookup"><span data-stu-id="be360-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="be360-128">Festlegen von Assemblyattributen</span><span class="sxs-lookup"><span data-stu-id="be360-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="be360-129">Beschreibt Assemblyattribute und wie diese festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="be360-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="be360-130">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="be360-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="be360-131">Beschreibt, wie und warum Sie eine Assembly mit einem starken Namen signieren und enthält Themen zur Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="be360-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="be360-132">Verzögertes Signieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="be360-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="be360-133">Beschreibt, wie eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="be360-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="be360-134">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="be360-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="be360-135">Beschreibt, wie und warum Sie Assemblys zum globalen Assemblycache hinzufügen und enthält Themen zur Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="be360-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="be360-136">Gewusst wie: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="be360-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="be360-137">Beschreibt, wie Sie MSIL Disassembler (Ildasm.exe) zum Anzeigen von Assemblyinhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="be360-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="be360-138">Typweiterleitung in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="be360-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="be360-139">Beschreibt, wie die Typweiterleitung zum Verschieben eines Typs in eine andere Assembly verwendet wird, ohne dass vorhandene Anwendungen unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="be360-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="be360-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="be360-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="be360-141">Die .NET Framework-Klasse, die eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="be360-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="be360-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="be360-142">Related Sections</span></span>  
 [<span data-ttu-id="be360-143">Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="be360-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="be360-144">Beschreibt, wie Typen oder andere Informationen programmgesteuert von einer Assembly abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="be360-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="be360-145">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="be360-145">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="be360-146">Konzeptuelle Übersicht über Assemblys der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="be360-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="be360-147">Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="be360-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="be360-148">Bietet eine Übersicht zur Bindung von Assemblys und der <xref:System.Reflection.AssemblyVersionAttribute>- und <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribute.</span><span class="sxs-lookup"><span data-stu-id="be360-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="be360-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="be360-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="be360-150">Beschreibt, wie die Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be360-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="be360-151">Reflexion</span><span class="sxs-lookup"><span data-stu-id="be360-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="be360-152">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="be360-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

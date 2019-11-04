---
title: Programmieren mit Assemblys
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
ms.openlocfilehash: 9f07d36d9e47189d53e367fd1406e5684c024aa3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107057"
---
# <a name="program-with-assemblies"></a><span data-ttu-id="c30cf-102">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="c30cf-102">Program with assemblies</span></span>
<span data-ttu-id="c30cf-103">Assemblys sind die Bausteine von .NET Framework; sie bilden das Fundament für Bereitstellung, Versionskontrolle, Wiederverwendung, Gültigkeitsbereiche für die Aktivierung und Sicherheitsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="c30cf-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="c30cf-104">Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="c30cf-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="c30cf-105">Sie ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="c30cf-106">Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="c30cf-107">In diesem Abschnitt wird beschrieben, wie Module, Assembys aus Modulen und ein Schlüsselpaar erstellt werden, wie eine Assembly mit einem starken Namen signiert wird und wie eine Assembly im globalen Assemblycache installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c30cf-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="c30cf-108">Dieser Abschnitt beschreibt zusätzlich, wie Sie [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Informationen aus dem Assemblymanifest anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c30cf-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c30cf-109">Ab der .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladenen Runtime besitzt.</span><span class="sxs-lookup"><span data-stu-id="c30cf-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="c30cf-110">Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="c30cf-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c30cf-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c30cf-111">In this section</span></span>  
 [<span data-ttu-id="c30cf-112">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="c30cf-112">Create assemblies</span></span>](create.md)  
 <span data-ttu-id="c30cf-113">Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.</span><span class="sxs-lookup"><span data-stu-id="c30cf-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="c30cf-114">Assemblynamen</span><span class="sxs-lookup"><span data-stu-id="c30cf-114">Assembly names</span></span>](names.md)  
 <span data-ttu-id="c30cf-115">Bietet eine Übersicht über die Assemblybenennung.</span><span class="sxs-lookup"><span data-stu-id="c30cf-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="c30cf-116">Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly</span><span class="sxs-lookup"><span data-stu-id="c30cf-116">How to: Determine an assembly's fully qualified name</span></span>](find-fully-qualified-name.md)  
 <span data-ttu-id="c30cf-117">Beschreibt, wie der vollqualifizierte Namen einer Assembly bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c30cf-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="c30cf-118">Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="c30cf-118">Run intranet applications in full trust</span></span>](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="c30cf-119">Beschreibt, wie Legacysicherheitsrichtlinien für voll vertrauenswürdige Assemblys in einer Intranetfreigabe angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="c30cf-120">Assemblyspeicherort</span><span class="sxs-lookup"><span data-stu-id="c30cf-120">Assembly location</span></span>](location.md)  
 <span data-ttu-id="c30cf-121">Bietet eine Übersicht, wo Assemblys zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="c30cf-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="c30cf-122">Vorgehensweise: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="c30cf-122">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)  
 <span data-ttu-id="c30cf-123">Beschreibt das Erstellen einer Assembly mit einer einzigen Datei.</span><span class="sxs-lookup"><span data-stu-id="c30cf-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="c30cf-124">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="c30cf-124">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="c30cf-125">Beschreibt Gründe für das Erstellen von Assemblys mit mehreren Dateien.</span><span class="sxs-lookup"><span data-stu-id="c30cf-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="c30cf-126">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="c30cf-126">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)  
 <span data-ttu-id="c30cf-127">Beschreibt das Erstellen einer Assembly mit mehreren Dateien.</span><span class="sxs-lookup"><span data-stu-id="c30cf-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="c30cf-128">Festlegen von Assemblyattributen</span><span class="sxs-lookup"><span data-stu-id="c30cf-128">Set assembly attributes</span></span>](set-attributes.md)  
 <span data-ttu-id="c30cf-129">Beschreibt Assemblyattribute und wie diese festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="c30cf-130">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="c30cf-130">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)  
 <span data-ttu-id="c30cf-131">Beschreibt, wie und warum Sie eine Assembly mit einem starken Namen signieren und enthält Themen zur Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="c30cf-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="c30cf-132">Verzögertes Signieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="c30cf-132">Delay-sign an assembly</span></span>](delay-sign.md)  
 <span data-ttu-id="c30cf-133">Beschreibt, wie eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="c30cf-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="c30cf-134">Arbeiten mit Assemblys und dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="c30cf-134">Work with assemblies and the global assembly cache</span></span>](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="c30cf-135">Beschreibt, wie und warum Sie Assemblys zum globalen Assemblycache hinzufügen und enthält Themen zur Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="c30cf-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="c30cf-136">Vorgehensweise: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="c30cf-136">How to: View assembly contents</span></span>](view-contents.md)  
 <span data-ttu-id="c30cf-137">Beschreibt, wie Sie MSIL Disassembler (Ildasm.exe) zum Anzeigen von Assemblyinhalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="c30cf-138">Typweiterleitung in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c30cf-138">Type forwarding in the common language runtime</span></span>](type-forwarding.md)  
 <span data-ttu-id="c30cf-139">Beschreibt, wie die Typweiterleitung zum Verschieben eines Typs in eine andere Assembly verwendet wird, ohne dass vorhandene Anwendungen unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c30cf-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="c30cf-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="c30cf-141">Die .NET Framework-Klasse, die eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="c30cf-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c30cf-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c30cf-142">Related sections</span></span>  
 [<span data-ttu-id="c30cf-143">Vorgehensweise: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="c30cf-143">How to: Obtain type and member information from an assembly</span></span>](../../framework/reflection-and-codedom/get-type-member-information.md)  
 <span data-ttu-id="c30cf-144">Beschreibt, wie Typen oder andere Informationen programmgesteuert von einer Assembly abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c30cf-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="c30cf-145">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="c30cf-145">Assemblies in .NET</span></span>](index.md)  
 <span data-ttu-id="c30cf-146">Konzeptuelle Übersicht über Assemblys der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c30cf-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="c30cf-147">Versionsverwaltung für Assemblys</span><span class="sxs-lookup"><span data-stu-id="c30cf-147">Assembly versioning</span></span>](versioning.md)  
 <span data-ttu-id="c30cf-148">Bietet eine Übersicht zur Bindung von Assemblys und der <xref:System.Reflection.AssemblyVersionAttribute>- und <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribute.</span><span class="sxs-lookup"><span data-stu-id="c30cf-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="c30cf-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="c30cf-149">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="c30cf-150">Beschreibt, wie die Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c30cf-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 <span data-ttu-id="c30cf-151">[Reflection (Reflektion)](../../framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="c30cf-151">[Reflection](../../framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="c30cf-152">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c30cf-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>

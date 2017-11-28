---
title: "Anwendungskompatibilität im .NET Framework"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: "19"
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e67fff19c4b187010b35519081f46e11effbad6c
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2017
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="619f9-102">Anwendungskompatibilität im .NET Framework</span><span class="sxs-lookup"><span data-stu-id="619f9-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="619f9-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="619f9-103">Introduction</span></span>
<span data-ttu-id="619f9-104">Kompatibilität ist ein wichtiges Ziel jedes .NET-Release.</span><span class="sxs-lookup"><span data-stu-id="619f9-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="619f9-105">Durch Kompatibilität wird sichergestellt, dass jede Version additiv ist; frühere Versionen funktionieren also weiterhin.</span><span class="sxs-lookup"><span data-stu-id="619f9-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="619f9-106">Auf der anderen Seite können Änderungen an früheren Versionen (zur Leistungssteigerung, Beheben von Sicherheitsproblemen oder Fehlerbehebungen) zu Kompatibilitätsproblemen im vorhandenen Code oder Anwendungen führen, die unter einer späteren Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="619f9-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="619f9-107">.NET Framework erkennt Änderungen der Neuzuweisung und Laufzeitänderungen.</span><span class="sxs-lookup"><span data-stu-id="619f9-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="619f9-108">Die Neuzuweisung von Änderungen beeinflussen Anwendungen, die auf eine bestimmte .NET Framework-Version abzielen, aber auf einer höheren Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="619f9-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="619f9-109">Laufzeitänderungen betreffen alle Anwendungen, die auf einer bestimmten Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="619f9-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="619f9-110">Jede App hat eine bestimmte Version von .NET Framework als Ziel, die durch Folgendes angegeben werden kann:</span><span class="sxs-lookup"><span data-stu-id="619f9-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

* <span data-ttu-id="619f9-111">Definieren eines Zielframeworks in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="619f9-111">Defining a target framework in Visual Studio.</span></span>
* <span data-ttu-id="619f9-112">Angeben des Zielframeworks in einer Projektdatei</span><span class="sxs-lookup"><span data-stu-id="619f9-112">Specifying the target framework in a project file.</span></span>
* <span data-ttu-id="619f9-113">Anwenden einer <xref:System.Runtime.Versioning.TargetFrameworkAttribute> auf dem Quellcode</span><span class="sxs-lookup"><span data-stu-id="619f9-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="619f9-114">Wenn .NET Framework auf einer neueren Version anstatt auf der beabsichtigten ausgeführt wird, wird ein besonderes Verhalten angewendet, um die ältere Zielversion zu imitieren.</span><span class="sxs-lookup"><span data-stu-id="619f9-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="619f9-115">Anders ausgedrückt: Die App wird auf der neueren Version des Framework ausgeführt, sich aber so verhalten, als würde sie auf der älteren Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="619f9-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="619f9-116">Viele Kompatibilitätsprobleme zwischen den .NET Framework-Versionen werden durch dieses besondere Modell minimiert.</span><span class="sxs-lookup"><span data-stu-id="619f9-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="619f9-117">Laufzeitänderungen</span><span class="sxs-lookup"><span data-stu-id="619f9-117">Runtime changes</span></span>

<span data-ttu-id="619f9-118">Laufzeitprobleme tauchen auf, wenn eine neue Laufzeit auf einem Gerät bereitgestellt wird und wenn die gleichen Binärdateien ausgeführt werden, es jedoch zu anderem Verhalten kommt.</span><span class="sxs-lookup"><span data-stu-id="619f9-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="619f9-119">Wenn eine Binärdatei für .NET Framework 4.0 kompiliert wurde, wird Sie im .NET Framework 4.0-Kompatibilitätsmodus auf 4.5 oder späteren Versionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="619f9-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="619f9-120">Viele Änderungen, die 4.5 betreffen, werden für 4.0 kompilierte Binärdateien nicht betreffen.</span><span class="sxs-lookup"><span data-stu-id="619f9-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="619f9-121">Dies ist spezifisch für AppDomain und ist von den Einstellungen der Einstiegsassembly abhängig.</span><span class="sxs-lookup"><span data-stu-id="619f9-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="619f9-122">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="619f9-122">Retargeting changes</span></span>

<span data-ttu-id="619f9-123">Probleme bei der Neuzuweisung erscheinen, wenn eine Assembly, die ursprünglich 4.0 angepeilt hat, nun 4.5 als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="619f9-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="619f9-124">Die Assembly wählt nun die neuen Funktionen sowie die potenziellen Kompatibilitätsprobleme für alte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="619f9-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="619f9-125">Dies wird erneut von der Einstiegsassembly bestimmt, also von der Konsolen-App, die die Assembly verwendet oder der Website, die auf die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="619f9-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="619f9-126">Diagnose der .NET-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="619f9-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="619f9-127">Die Diagnose der .NET Kompatibilität umfasst von Roslyn unterstützte Analyzer, die bei der Erkennung von Anwendungskompatibilitätsproblemen zwischen .NET Framework-Versionen helfen.</span><span class="sxs-lookup"><span data-stu-id="619f9-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="619f9-128">Diese Liste enthält alle verfügbaren Analyzer, obwohl nur eine Teilmenge auf eine bestimmte Migration angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="619f9-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="619f9-129">Die Analyzer ermitteln, welche Probleme auf die geplante Migration zutreffen und beschreibt diese nur kurz.</span><span class="sxs-lookup"><span data-stu-id="619f9-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="619f9-130">Jedes Problem umfasst die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="619f9-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="619f9-131">Die Beschreibung der Änderungen von einer früheren Version.</span><span class="sxs-lookup"><span data-stu-id="619f9-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="619f9-132">Wie sich die Änderung auf Kunden auswirkt und ob Problemumgehungen verfügbar sind, um die Kompatibilität zwischen Versionen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="619f9-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="619f9-133">Eine Bewertung der Bedeutung der Änderung.</span><span class="sxs-lookup"><span data-stu-id="619f9-133">An assessment of how important the change is.</span></span> <span data-ttu-id="619f9-134">Anwendungskompatibilitätsprobleme werden wie folgt kategorisiert:</span><span class="sxs-lookup"><span data-stu-id="619f9-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="619f9-135">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="619f9-135">Major</span></span>|<span data-ttu-id="619f9-136">Eine wesentliche Änderung, die eine große Anzahl von Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="619f9-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="619f9-137">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="619f9-137">Minor</span></span>|<span data-ttu-id="619f9-138">Eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="619f9-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="619f9-139">Grenzfall</span><span class="sxs-lookup"><span data-stu-id="619f9-139">Edge case</span></span>|<span data-ttu-id="619f9-140">Eine Änderung, die nur Apps in sehr spezifischen, nicht üblichen Szenarien beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="619f9-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="619f9-141">Transparent</span><span class="sxs-lookup"><span data-stu-id="619f9-141">Transparent</span></span>|<span data-ttu-id="619f9-142">Eine Änderung ohne nennenswerte Auswirkungen auf die Entwickler oder Benutzer der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="619f9-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="619f9-143">Die Version gibt an, wann die Änderung zum ersten Mal im Framework auftritt.</span><span class="sxs-lookup"><span data-stu-id="619f9-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="619f9-144">Einige der Änderungen werden in einer bestimmten Version eingeführt und in einer späteren Version zurückgesetzt; dies wird ebenso beschrieben.</span><span class="sxs-lookup"><span data-stu-id="619f9-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="619f9-145">Art der Änderung:</span><span class="sxs-lookup"><span data-stu-id="619f9-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="619f9-146">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="619f9-146">Retargeting</span></span>|<span data-ttu-id="619f9-147">Die Änderung wirkt sich auf Apps aus, die neu kompiliert werden, um auf eine neue Version von .NET Framework ausgerichtet zu werden.</span><span class="sxs-lookup"><span data-stu-id="619f9-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="619f9-148">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="619f9-148">Runtime</span></span>|<span data-ttu-id="619f9-149">Die Änderung wirkt sich auf eine vorhandene Anwendung aus, die auf eine frühere Version von .NET Framework ausgerichtet ist, aber unter einer höheren Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="619f9-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="619f9-150">Die betroffenen APIs, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="619f9-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="619f9-151">Die IDs der verfügbaren Diagnosen.</span><span class="sxs-lookup"><span data-stu-id="619f9-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="619f9-152">Verwendung</span><span class="sxs-lookup"><span data-stu-id="619f9-152">Usage</span></span>
<span data-ttu-id="619f9-153">Um zu starten, wählen Sie unten den Typ der Kompatibilitätsänderung aus:</span><span class="sxs-lookup"><span data-stu-id="619f9-153">To begin, select the type of compatibility change below:</span></span>

* [<span data-ttu-id="619f9-154">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="619f9-154">Retargeting Changes</span></span>](./retargeting/index.md)
* [<span data-ttu-id="619f9-155">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="619f9-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="619f9-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="619f9-156">See Also</span></span>

* [<span data-ttu-id="619f9-157">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="619f9-157">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
* [<span data-ttu-id="619f9-158">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="619f9-158">What's New</span></span>](../../../docs/framework/whats-new/index.md)
* [<span data-ttu-id="619f9-159">Veraltete Elemente in der Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="619f9-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)

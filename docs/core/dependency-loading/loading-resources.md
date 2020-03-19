---
title: Ladealgorithmus für Satellitenassemblys – .NET Core
description: Beschreibung von Details des Ladealgorithmus für Satellitenassemblys in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303623"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="12a3f-103">Ladealgorithmus für Satellitenassemblys</span><span class="sxs-lookup"><span data-stu-id="12a3f-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="12a3f-104">Satellitenassemblys werden verwendet, um lokalisierte Ressourcen für Sprachen und Kulturen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="12a3f-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="12a3f-105">Für Satellitenassemblys wird ein anderer Ladealgorithmus als für allgemeine verwaltete Assemblys verwendet.</span><span class="sxs-lookup"><span data-stu-id="12a3f-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="12a3f-106">Wann werden Satellitenassemblys geladen?</span><span class="sxs-lookup"><span data-stu-id="12a3f-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="12a3f-107">Satellitenassemblys werden beim Laden einer lokalisierten Ressource geladen.</span><span class="sxs-lookup"><span data-stu-id="12a3f-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="12a3f-108">Die grundlegende API zum Laden lokalisierter Ressourcen ist die <xref:System.Resources.ResourceManager?displayProperty=fullName>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="12a3f-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="12a3f-109">Letztendlich ruft die <xref:System.Resources.ResourceManager>-Klasse die <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A>-Methode für jede <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="12a3f-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="12a3f-110">APIs auf höherer Ebene können eine API auf niedrigerer Ebene abstrahieren.</span><span class="sxs-lookup"><span data-stu-id="12a3f-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="12a3f-111">Algorithmus</span><span class="sxs-lookup"><span data-stu-id="12a3f-111">Algorithm</span></span>

<span data-ttu-id="12a3f-112">Der .NET Core-Ressourcenfallbackprozess besteht aus folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="12a3f-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="12a3f-113">Bestimmen Sie die `active` <xref:System.Runtime.Loader.AssemblyLoadContext>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="12a3f-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="12a3f-114">In allen Fällen handelt es sich bei der `active`-Instanz um den <xref:System.Runtime.Loader.AssemblyLoadContext> der ausführenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="12a3f-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="12a3f-115">Die `active`-Instanz versucht, eine Satellitenassembly für die angeforderte Kultur in folgender Reihenfolge nach Priorität zu laden:</span><span class="sxs-lookup"><span data-stu-id="12a3f-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="12a3f-116">Überprüfen des Caches</span><span class="sxs-lookup"><span data-stu-id="12a3f-116">Checking its cache.</span></span>
    - <span data-ttu-id="12a3f-117">Überprüfen des Verzeichnisses der aktuell ausgeführten Assembly auf ein Unterverzeichnis, das der angeforderten <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> entspricht (z. B. `es-MX`)</span><span class="sxs-lookup"><span data-stu-id="12a3f-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="12a3f-118">Diese Funktion wurde erst ab .NET Core 3.0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="12a3f-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="12a3f-119">Unter Linux und macOS muss beim Unterverzeichnis die Groß-/Kleinschreibung beachtet werden, und eine der folgenden Voraussetzungen muss erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="12a3f-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        > - <span data-ttu-id="12a3f-120">Die Groß-/Kleinschreibung muss genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="12a3f-120">Exactly match case.</span></span>
        > - <span data-ttu-id="12a3f-121">Es wurden nur Kleinbuchstaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="12a3f-121">Be in lower case.</span></span>

    - <span data-ttu-id="12a3f-122">Wenn `active` die <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>-Instanz ist, durch Ausführen der Logik für [Standardüberprüfungen von Satellitenassemblys (Ressourcen) ](default-probing.md#satellite-resource-assembly-probing).</span><span class="sxs-lookup"><span data-stu-id="12a3f-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="12a3f-123">Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>-Funktion</span><span class="sxs-lookup"><span data-stu-id="12a3f-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="12a3f-124">Auslösen des <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="12a3f-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="12a3f-125">Auslösen des <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="12a3f-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="12a3f-126">Wenn eine Satellitenassembly geladen wird:</span><span class="sxs-lookup"><span data-stu-id="12a3f-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="12a3f-127">Das <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>-Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="12a3f-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="12a3f-128">Die Assembly wird nach der angeforderten Ressource durchsucht.</span><span class="sxs-lookup"><span data-stu-id="12a3f-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="12a3f-129">Wenn die Runtime die Ressource in der Assembly findet, verwendet sie diese.</span><span class="sxs-lookup"><span data-stu-id="12a3f-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="12a3f-130">Wenn sie die Ressource nicht findet, fährt sie mit der Suche fort.</span><span class="sxs-lookup"><span data-stu-id="12a3f-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12a3f-131">Um eine Ressource in der Satellitenassembly zu finden, sucht die Runtime nach der Ressourcendatei, die vom <xref:System.Resources.ResourceManager> für den aktuellen <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="12a3f-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="12a3f-132">Sie sucht in der Ressourcendatei nach dem angeforderten Ressourcennamen.</span><span class="sxs-lookup"><span data-stu-id="12a3f-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="12a3f-133">Wenn keins von beiden gefunden wird, wird die Ressource als nicht gefunden behandelt.</span><span class="sxs-lookup"><span data-stu-id="12a3f-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="12a3f-134">Als Nächstes sucht die Runtime die Assemblys der übergeordneten Kultur über viele mögliche Ebenen hinweg, wobei jedes Mal die Schritte 2 und 3 wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="12a3f-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="12a3f-135">Jeder Kultur hat genau ein übergeordnetes Element, das von der <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>-Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="12a3f-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="12a3f-136">Die Suche nach übergeordneten Kulturen ist beendet, wenn die <xref:System.Globalization.CultureInfo.Parent%2A>-Eigenschaft einer Kultur <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="12a3f-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="12a3f-137">Für die <xref:System.Globalization.CultureInfo.InvariantCulture> werden die Schritte 2 und 3 nicht wiederholt, sondern stattdessen mit Schritt 5 fortgefahren.</span><span class="sxs-lookup"><span data-stu-id="12a3f-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="12a3f-138">Wenn die Ressource immer noch nicht gefunden wurde, wird die Ressource für die Standardkultur (Fallback) verwendet.</span><span class="sxs-lookup"><span data-stu-id="12a3f-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="12a3f-139">Für gewöhnlich werden die Ressourcen der Standardkultur in die Hauptassembly der Anwendung integriert.</span><span class="sxs-lookup"><span data-stu-id="12a3f-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="12a3f-140">Sie können jedoch <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> für die <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="12a3f-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="12a3f-141">Dieser Wert gibt an, dass der endgültige Fallbackort für Ressourcen eine Satellitenassembly ist und nicht die Hauptassembly.</span><span class="sxs-lookup"><span data-stu-id="12a3f-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12a3f-142">Die Standardkultur wird als endgültiges Fallback verwendet.</span><span class="sxs-lookup"><span data-stu-id="12a3f-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="12a3f-143">Daher wird empfohlen, immer einen umfassenden Satz an Ressourcen in die Standardressourcendatei zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="12a3f-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="12a3f-144">So werden Ausnahmen verhindert.</span><span class="sxs-lookup"><span data-stu-id="12a3f-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="12a3f-145">Über diesen umfassenden Satz stellen Sie einen Fallback für alle Ressourcen bereit und stellen sicher, dass immer mindestens eine Ressource für den Benutzer verfügbar ist, auch wenn diese nicht kulturspezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="12a3f-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="12a3f-146">Zum Schluss:</span><span class="sxs-lookup"><span data-stu-id="12a3f-146">Finally,</span></span>
   - <span data-ttu-id="12a3f-147">Wenn die Runtime keine Ressourcendatei für eine Standardkultur (Fallback) findet, wird eine <xref:System.Resources.MissingManifestResourceException> oder <xref:System.Resources.MissingSatelliteAssemblyException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="12a3f-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="12a3f-148">Wenn die Ressourcendatei gefunden wurde, aber die angeforderte Ressource nicht vorhanden ist, gibt die Anforderung `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="12a3f-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>

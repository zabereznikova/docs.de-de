---
title: '&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8ae2c87a135c8ef9a43b6d11a62b833ef43c9a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681000"
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="65024-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span><span class="sxs-lookup"><span data-stu-id="65024-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="65024-103">Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="65024-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="65024-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="65024-104">\<configuration></span></span>  
<span data-ttu-id="65024-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="65024-105">\<runtime></span></span>  
<span data-ttu-id="65024-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="65024-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65024-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="65024-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65024-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65024-108">Attributes and Elements</span></span>  
 <span data-ttu-id="65024-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65024-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65024-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="65024-110">Attributes</span></span>  
  
|<span data-ttu-id="65024-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="65024-111">Attribute</span></span>|<span data-ttu-id="65024-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65024-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="65024-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="65024-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="65024-114">Gibt an, ob "PerfCounter.dll" die registrierungseinstellung CategoryOptions verwendet, um zu ermitteln, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutzten Speicher oder globalen Arbeitsspeicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="65024-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="65024-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="65024-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="65024-116">Wert</span><span class="sxs-lookup"><span data-stu-id="65024-116">Value</span></span>|<span data-ttu-id="65024-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65024-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="65024-118">"PerfCounter.dll" verwendet nicht die CategoryOptions Registrierung durch Festlegen dieses Werts ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="65024-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="65024-119">"PerfCounter.dll" wird die registrierungseinstellung CategoryOptions verwendet.</span><span class="sxs-lookup"><span data-stu-id="65024-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65024-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65024-120">Child Elements</span></span>  
 <span data-ttu-id="65024-121">Keine</span><span class="sxs-lookup"><span data-stu-id="65024-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65024-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65024-122">Parent Elements</span></span>  
  
|<span data-ttu-id="65024-123">Element</span><span class="sxs-lookup"><span data-stu-id="65024-123">Element</span></span>|<span data-ttu-id="65024-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65024-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="65024-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="65024-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="65024-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="65024-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65024-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65024-127">Remarks</span></span>  
 <span data-ttu-id="65024-128">In Versionen von .NET Framework vor der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die Version von "PerfCounter.dll", die geladen wurden entsprach, für die Laufzeit, die im Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="65024-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="65024-129">Bei ein Computer sowohl .NET Framework, Version 1.1 und [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installiert haben, eine .NET Framework 1.1-Anwendung lädt die .NET Framework 1.1-Version von "PerfCounter.dll".</span><span class="sxs-lookup"><span data-stu-id="65024-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="65024-130">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], die neueste installierte Version von "PerfCounter.dll" wird geladen.</span><span class="sxs-lookup"><span data-stu-id="65024-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="65024-131">Dies bedeutet, dass eine .NET Framework 1.1-Anwendung lädt die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Version von "PerfCounter.dll" Wenn die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="65024-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="65024-132">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], bei der Nutzung von Leistungsindikatoren überprüft "PerfCounter.dll" CategoryOptions Registrierungseintrag für jeden Anbieter, um zu bestimmen, ob er aus kategoriespezifischem, gemeinsam genutzten Speicher oder der globale freigegebene Speicher lesen soll.</span><span class="sxs-lookup"><span data-stu-id="65024-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="65024-133">Die .NET Framework 1.1 PerfCounter.dll Lesen dieses Registrierungseintrags nicht, da es nicht an gemeinsam genutztem Speicher kategoriespezifische bekannt ist; Es liest aus der globale freigegebene Speicher.</span><span class="sxs-lookup"><span data-stu-id="65024-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="65024-134">Für die Abwärtskompatibilität der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] "PerfCounter.dll" überprüft nicht den Registrierungseintrag "CategoryOptions" aus, wenn in einer .NET Framework 1.1-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65024-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="65024-135">Sie verwendet einfach globalen freigegebenen Speicher, genau wie die .NET Framework 1.1 "PerfCounter.dll".</span><span class="sxs-lookup"><span data-stu-id="65024-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="65024-136">Sie können jedoch anweisen, die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] "PerfCounter.dll" Überprüfen Sie die registrierungseinstellung durch Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element.</span><span class="sxs-lookup"><span data-stu-id="65024-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65024-137">Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element garantiert nicht, dass kategoriespezifische gemeinsam genutzten Speicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65024-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="65024-138">Aktivierter Einstellung `true` bewirkt nur, dass "PerfCounter.dll", um auf die registrierungseinstellung CategoryOptions zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="65024-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="65024-139">Die Standardeinstellung für CategoryOptions ist die Verwendung von gemeinsam genutzten Speicher kategoriespezifische; Sie können jedoch ändern, dass CategoryOptions, um anzugeben, dass der globaler freigegebener Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65024-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="65024-140">Der Registrierungsschlüssel, der die Einstellung der CategoryOptions enthält ist HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< "CategoryName"\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="65024-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="65024-141">Standardmäßig wird CategoryOptions auf 3 festgelegt "PerfCounter.dll" weist kategoriespezifische freigegebenen Speicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="65024-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="65024-142">Wenn CategoryOptions auf 0 festgelegt ist, wird "PerfCounter.dll" globalen freigegebenen Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="65024-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="65024-143">Instanzdaten werden wiederverwendet werden, nur, wenn der Name des zu erstellenden Instanz mit der Instanz, die wiederverwendet werden identisch ist.</span><span class="sxs-lookup"><span data-stu-id="65024-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="65024-144">Alle Versionen werden in der Kategorie "" schreiben.</span><span class="sxs-lookup"><span data-stu-id="65024-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="65024-145">Wenn CategoryOptions auf 1 festgelegt ist, globaler freigegebener Speicher wird verwendet, aber Instanzdaten wiederverwendet werden können, den Namen der Kategorie ist die gleiche Länge wie der Kategorie, die wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65024-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="65024-146">Die Einstellungen, 0 und 1 können der schnell an Größe zunimmt Leistungsindikator-Arbeitsspeichers zu Speicherverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="65024-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65024-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65024-147">Example</span></span>  
 <span data-ttu-id="65024-148">Das folgende Beispiel zeigt, wie Sie angeben, dass "PerfCounter.dll" verweisen soll, den Registrierungseintrag CategoryOptions, um festzustellen, ob kategoriespezifische gemeinsam genutzten Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65024-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65024-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65024-149">See also</span></span>
- [<span data-ttu-id="65024-150">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="65024-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="65024-151">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="65024-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: '&lt;ForcePerformanceCounterUniqueSharedMemoryReads&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1f041cbfb4195b2c649c3af4fa061bf63e227df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="f7df2-102">&lt;ForcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span><span class="sxs-lookup"><span data-stu-id="f7df2-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="f7df2-103">Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f7df2-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="f7df2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f7df2-104">\<configuration></span></span>  
<span data-ttu-id="f7df2-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="f7df2-105">\<runtime></span></span>  
<span data-ttu-id="f7df2-106">\<ForcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="f7df2-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7df2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7df2-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7df2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f7df2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f7df2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7df2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7df2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f7df2-110">Attributes</span></span>  
  
|<span data-ttu-id="f7df2-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f7df2-111">Attribute</span></span>|<span data-ttu-id="f7df2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7df2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f7df2-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f7df2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7df2-114">Gibt an, ob PerfCounter.dll die registrierungseinstellung "CategoryOptions" verwendet, um zu bestimmen, ob beim Laden von Leistungsindikatordaten aus kategoriespezifische freigegebenen Speicher oder globalen Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f7df2-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f7df2-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f7df2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f7df2-116">Wert</span><span class="sxs-lookup"><span data-stu-id="f7df2-116">Value</span></span>|<span data-ttu-id="f7df2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7df2-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f7df2-118">PerfCounter.dll verwendet nicht die CategoryOptions registrierungseinstellung Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f7df2-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="f7df2-119">PerfCounter.dll wird die registrierungseinstellung "CategoryOptions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7df2-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7df2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7df2-120">Child Elements</span></span>  
 <span data-ttu-id="f7df2-121">Keine</span><span class="sxs-lookup"><span data-stu-id="f7df2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7df2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7df2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f7df2-123">Element</span><span class="sxs-lookup"><span data-stu-id="f7df2-123">Element</span></span>|<span data-ttu-id="f7df2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7df2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f7df2-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f7df2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f7df2-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f7df2-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7df2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7df2-127">Remarks</span></span>  
 <span data-ttu-id="f7df2-128">In Versionen von .NET Framework vor der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die Version von PerfCounter.dll, das geladen wurde zugestimmt haben, für die Laufzeit, die im Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f7df2-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="f7df2-129">Wenn ein Computer sowohl .NET Framework, Version 1.1 wurde und die [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installiert ist, würde eine .NET Framework 1.1-Anwendung die .NET Framework 1.1-Version von PerfCounter.dll laden.</span><span class="sxs-lookup"><span data-stu-id="f7df2-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="f7df2-130">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], die neueste installierte Version von PerfCounter.dll geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f7df2-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="f7df2-131">Dies bedeutet, dass eine .NET Framework 1.1-Anwendung geladen werden die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Version von PerfCounter.dll Wenn die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f7df2-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="f7df2-132">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], bei der Nutzung von Leistungsindikatoren überprüft PerfCounter.dll den CategoryOptions-Registrierungseintrag für jeden Anbieter, um zu bestimmen, ob von kategoriespezifische freigegebenen Speicher oder der globale freigegebene Speicher gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7df2-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="f7df2-133">Die .NET Framework 1.1 PerfCounter.dll Lesen dieser Registrierungseintrag nicht, da es nicht an gemeinsam genutztem Speicher kategoriespezifische bekannt ist; Er liest immer aus der globale freigegebene Speicher.</span><span class="sxs-lookup"><span data-stu-id="f7df2-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="f7df2-134">Für die Abwärtskompatibilität der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll überprüft nicht den Registrierungseintrag CategoryOptions, bei der Ausführung in einer .NET Framework 1.1-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f7df2-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="f7df2-135">Globalen freigegebenen Speicher, genau wie die .NET Framework 1.1 PerfCounter.dll einfach verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7df2-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="f7df2-136">Sie können jedoch anweisen, die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll, überprüfen Sie die Einstellung in der Registrierung durch Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element.</span><span class="sxs-lookup"><span data-stu-id="f7df2-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7df2-137">Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element kann nicht garantiert, dass kategoriespezifische freigegebener Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7df2-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="f7df2-138">Aktivierter Einstellung `true` nur bewirkt, dass PerfCounter.dll auf die registrierungseinstellung "CategoryOptions" verweisen.</span><span class="sxs-lookup"><span data-stu-id="f7df2-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="f7df2-139">Die Standardeinstellung für CategoryOptions ist die Verwendung von gemeinsam genutzten Speicher kategoriespezifische; Sie können jedoch ändern, dass CategoryOptions, um anzugeben, dass der globaler freigegebener Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7df2-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="f7df2-140">Der Registrierungsschlüssel, die die Einstellung CategoryOptions enthält, ist HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< CategoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="f7df2-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="f7df2-141">Standardmäßig wird CategoryOptions auf 3 festgelegt PerfCounter.dll weist kategoriespezifische freigegebenen Speicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7df2-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="f7df2-142">Wenn CategoryOptions auf 0 festgelegt ist, verwendet PerfCounter.dll globalen freigegebenen Speicher.</span><span class="sxs-lookup"><span data-stu-id="f7df2-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="f7df2-143">Instanzdaten werden nur dann, wenn der Name des zu erstellenden Instanz identisch mit der Instanz wird wiederverwendet wird wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="f7df2-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="f7df2-144">Alle Versionen werden in der Kategorie schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7df2-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="f7df2-145">Wenn CategoryOptions auf 1 festgelegt ist, globaler freigegebener Speicher verwendet, aber Instanzdaten können wiederverwendet werden, wenn Sie den Namen der Kategorie die gleiche Länge wie die Kategorie, die wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7df2-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="f7df2-146">Die Einstellungen, 0 und 1 können zu Speicherverlusten und das Transaktionsprotokoll der Leistungsindikator-Arbeitsspeichers führen.</span><span class="sxs-lookup"><span data-stu-id="f7df2-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7df2-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7df2-147">Example</span></span>  
 <span data-ttu-id="f7df2-148">Das folgende Beispiel zeigt, wie angegeben wird, dass PerfCounter.dll verweisen soll, den Registrierungseintrag CategoryOptions, um festzustellen, ob kategoriespezifische freigegebener Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7df2-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7df2-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7df2-149">See Also</span></span>  
 [<span data-ttu-id="f7df2-150">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7df2-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f7df2-151">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f7df2-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96d38abad37f9460230164de784a1258e7e937a4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663723"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="960cb-102">\<forceperformancecounteruniquesharedmemoryreads > Element</span><span class="sxs-lookup"><span data-stu-id="960cb-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="960cb-103">Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="960cb-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="960cb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="960cb-104">\<configuration></span></span>  
<span data-ttu-id="960cb-105">\<Lauf Zeit ></span><span class="sxs-lookup"><span data-stu-id="960cb-105">\<runtime></span></span>  
<span data-ttu-id="960cb-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="960cb-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="960cb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="960cb-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="960cb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="960cb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="960cb-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="960cb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="960cb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="960cb-110">Attributes</span></span>  
  
|<span data-ttu-id="960cb-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="960cb-111">Attribute</span></span>|<span data-ttu-id="960cb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="960cb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="960cb-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="960cb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="960cb-114">Gibt an, ob PerfCounter. dll die categoryoptions-Registrierungs Einstellung verwendet, um zu bestimmen, ob Leistungsdaten aus dem kategoriespezifischen freigegebenen oder globalen Arbeitsspeicher geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="960cb-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="960cb-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="960cb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="960cb-116">Wert</span><span class="sxs-lookup"><span data-stu-id="960cb-116">Value</span></span>|<span data-ttu-id="960cb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="960cb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="960cb-118">PerfCounter. dll verwendet nicht die Registrierungs Einstellung categoryoptions, dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="960cb-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="960cb-119">PerfCounter. dll verwendet die Registrierungs Einstellung categoryoptions.</span><span class="sxs-lookup"><span data-stu-id="960cb-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="960cb-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="960cb-120">Child Elements</span></span>  
 <span data-ttu-id="960cb-121">Keine</span><span class="sxs-lookup"><span data-stu-id="960cb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="960cb-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="960cb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="960cb-123">Element</span><span class="sxs-lookup"><span data-stu-id="960cb-123">Element</span></span>|<span data-ttu-id="960cb-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="960cb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="960cb-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="960cb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="960cb-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="960cb-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="960cb-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="960cb-127">Remarks</span></span>  
 <span data-ttu-id="960cb-128">In Versionen der .NET Framework vor dem .NET Framework 4 entsprach die Version von PerfCounter. dll, die geladen wurde, der Laufzeit, die in den Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="960cb-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="960cb-129">Wenn auf einem Computer sowohl der .NET Framework Version 1,1 als auch der .NET Framework 2,0 installiert war, würde eine .NET Framework 1,1-Anwendung die .NET Framework Version 1,1 von PerfCounter. dll laden.</span><span class="sxs-lookup"><span data-stu-id="960cb-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="960cb-130">Beginnend mit dem .NET Framework 4 wird die neueste installierte Version von "PerfCounter. dll" geladen.</span><span class="sxs-lookup"><span data-stu-id="960cb-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="960cb-131">Dies bedeutet, dass eine .NET Framework 1,1-Anwendung die .NET Framework 4-Version von "PerfCounter. dll" lädt, wenn die .NET Framework 4 auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="960cb-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="960cb-132">Beginnend mit dem .NET Framework 4 überprüft PerfCounter. dll bei der Nutzung von Leistungsindikatoren den Registrierungs Eintrag categoryoptions für jeden Anbieter, um zu bestimmen, ob er aus dem kategoriespezifischen freigegebenen Arbeitsspeicher oder dem globalen gemeinsam genutzten Speicher lesen soll.</span><span class="sxs-lookup"><span data-stu-id="960cb-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="960cb-133">Der .NET Framework 1,1 PerfCounter. dll liest diesen Registrierungs Eintrag nicht, da er keinen kategoriespezifischen freigegebenen Arbeitsspeicher kennt. Er liest immer aus dem globalen gemeinsam genutzten Speicher.</span><span class="sxs-lookup"><span data-stu-id="960cb-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="960cb-134">Aus Gründen der Abwärtskompatibilität überprüft das .NET Framework 4 PerfCounter. dll den Registrierungs Eintrag categoryoptions nicht, wenn er in einer .NET Framework 1,1-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="960cb-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="960cb-135">Es verwendet einfach den globalen gemeinsam genutzten Speicher, genau wie die .NET Framework 1,1 PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="960cb-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="960cb-136">Sie können jedoch die .NET Framework 4 PerfCounter. dll anweisen, die Registrierungs Einstellung durch Aktivieren des `<forcePerformanceCounterUniqueSharedMemoryReads>` -Elements zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="960cb-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="960cb-137">Das aktivieren `<forcePerformanceCounterUniqueSharedMemoryReads>` des-Elements garantiert nicht, dass kategoriespezifischer gemeinsam genutzter Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="960cb-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="960cb-138">Wenn die Einstellung `true` aktiviert ist, verweist PerfCounter. dll nur auf die Registrierungs Einstellung categoryoptions.</span><span class="sxs-lookup"><span data-stu-id="960cb-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="960cb-139">Die Standardeinstellung für categoryoptions ist die Verwendung des kategoriespezifischen freigegebenen Speichers. Sie können jedoch categoryoptions ändern, um anzugeben, dass der globale gemeinsame Arbeitsspeicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="960cb-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="960cb-140">Der Registrierungsschlüssel, der die Einstellung categoryoptions enthält,\\ist HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services < CategoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="960cb-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="960cb-141">Standardmäßig ist "categoryoptions" auf "3" festgelegt, was PerfCounter. dll anweist, kategoriespezifischen freigegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="960cb-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="960cb-142">Wenn categoryoptions auf 0 festgelegt ist, verwendet PerfCounter. dll globalen gemeinsam genutzten Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="960cb-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="960cb-143">Instanzdaten werden nur dann wieder verwendet, wenn der Name der Instanz, die erstellt wird, mit der Instanz identisch ist, die wieder verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="960cb-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="960cb-144">Alle Versionen können in die Kategorie schreiben.</span><span class="sxs-lookup"><span data-stu-id="960cb-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="960cb-145">Wenn categoryoptions auf 1 festgelegt ist, wird der globale freigegebene Speicher verwendet, aber Instanzdaten können wieder verwendet werden, wenn der Kategoriename dieselbe Länge wie die wiederverwendbare Kategorie hat.</span><span class="sxs-lookup"><span data-stu-id="960cb-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="960cb-146">Die Einstellungen 0 und 1 können zu Speicher Verlusten und zum Auffüllen des Leistungs Zählers führen.</span><span class="sxs-lookup"><span data-stu-id="960cb-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="960cb-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="960cb-147">Example</span></span>  
 <span data-ttu-id="960cb-148">Im folgenden Beispiel wird gezeigt, wie Sie angeben können, dass "PerfCounter. dll" auf den Registrierungs Eintrag "categoryoptions" verweisen soll, um zu bestimmen, ob der kategorisierte Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="960cb-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="960cb-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="960cb-149">See also</span></span>

- [<span data-ttu-id="960cb-150">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="960cb-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="960cb-151">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="960cb-151">Configuration File Schema</span></span>](../index.md)

---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154139"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="4403e-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="4403e-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="4403e-103">Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4403e-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="4403e-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4403e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4403e-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4403e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4403e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span><span class="sxs-lookup"><span data-stu-id="4403e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4403e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4403e-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4403e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4403e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4403e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4403e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4403e-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="4403e-110">Attributes</span></span>  
  
|<span data-ttu-id="4403e-111">attribute</span><span class="sxs-lookup"><span data-stu-id="4403e-111">Attribute</span></span>|<span data-ttu-id="4403e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4403e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4403e-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4403e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4403e-114">Gibt an, ob PerfCounter.dll die Registrierungseinstellung CategoryOptions verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem freigegebenem Speicher oder globalem Speicher geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4403e-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4403e-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="4403e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4403e-116">value</span><span class="sxs-lookup"><span data-stu-id="4403e-116">Value</span></span>|<span data-ttu-id="4403e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4403e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4403e-118">PerfCounter.dll verwendet nicht die KategorieOptions-Registrierungseinstellung Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4403e-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="4403e-119">PerfCounter.dll verwendet die Registrierungseinstellung CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="4403e-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4403e-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4403e-120">Child Elements</span></span>  
 <span data-ttu-id="4403e-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="4403e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4403e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4403e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4403e-123">Element</span><span class="sxs-lookup"><span data-stu-id="4403e-123">Element</span></span>|<span data-ttu-id="4403e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4403e-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4403e-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4403e-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4403e-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4403e-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4403e-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4403e-127">Remarks</span></span>  
 <span data-ttu-id="4403e-128">In Versionen von .NET Framework vor .NET Framework 4 entsprach die geladene Version von PerfCounter.dll der Laufzeit, die im Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4403e-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="4403e-129">Wenn auf einem Computer sowohl die .NET Framework Version 1.1 als auch die .NET Framework 2.0-Anwendung installiert wäre, würde eine .NET Framework 1.1-Anwendung die .NET Framework 1.1-Version von PerfCounter.dll laden.</span><span class="sxs-lookup"><span data-stu-id="4403e-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="4403e-130">Ab .NET Framework 4 wird die neueste installierte Version von PerfCounter.dll geladen.</span><span class="sxs-lookup"><span data-stu-id="4403e-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="4403e-131">Dies bedeutet, dass eine .NET Framework 1.1-Anwendung die .NET Framework 4-Version von PerfCounter.dll lädt, wenn .NET Framework 4 auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4403e-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="4403e-132">Ab .NET Framework 4 überprüft PerfCounter.dll beim Verwenden von Leistungsindikatoren den Registrierungseintrag CategoryOptions für jeden Anbieter, um zu ermitteln, ob er aus kategoriespezifischem freigegebenem Speicher oder globalem freigegebenem Speicher gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4403e-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="4403e-133">Der .NET Framework 1.1 PerfCounter.dll liest diesen Registrierungseintrag nicht, da er nicht über kategoriespezifischen freigegebenen Speicher informiert ist. es liest immer aus dem globalen freigegebenen Speicher.</span><span class="sxs-lookup"><span data-stu-id="4403e-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="4403e-134">Aus Gründen der Abwärtskompatibilität überprüft .NET Framework 4 PerfCounter.dll den Registrierungseintrag CategoryOptions nicht, wenn er in einer .NET Framework 1.1-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4403e-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="4403e-135">Es verwendet einfach globalen freigegebenen Speicher, genau wie .NET Framework 1.1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="4403e-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="4403e-136">Sie können jedoch die .NET Framework 4 PerfCounter.dll anweisen, `<forcePerformanceCounterUniqueSharedMemoryReads>` die Registrierungseinstellung zu überprüfen, indem Sie das Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4403e-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4403e-137">Das `<forcePerformanceCounterUniqueSharedMemoryReads>` Aktivieren des Elements garantiert nicht, dass kategoriespezifischer freigegebener Speicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4403e-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="4403e-138">Einstellung aktiviert, um `true` nur zu bewirken, dass PerfCounter.dll auf die Registrierungseinstellung CategoryOptions verweist.</span><span class="sxs-lookup"><span data-stu-id="4403e-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="4403e-139">Die Standardeinstellung für CategoryOptions ist die Verwendung kategoriespezifischer gemeinsam genutzter Speicher. Sie können jedoch CategoryOptions ändern, um anzugeben, dass globaler freigegebener Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4403e-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="4403e-140">Der Registrierungsschlüssel, der die KategorieOptions-Einstellung enthält, lautet\\ HKEY_LOCAL_MACHINE-System-CurrentControlSet-Dienste<kategorieName\>.</span><span class="sxs-lookup"><span data-stu-id="4403e-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="4403e-141">Standardmäßig ist CategoryOptions auf 3 festgelegt, was PerfCounter.dll anweist, kategoriespezifischen freigegebenen Speicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4403e-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="4403e-142">Wenn CategoryOptions auf 0 gesetzt ist, verwendet PerfCounter.dll globalen freigegebenen Speicher.</span><span class="sxs-lookup"><span data-stu-id="4403e-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="4403e-143">Instanzdaten werden nur wiederverwendet, wenn der Name der erstellten Instanz mit der wiederverwendeten Instanz identisch ist.</span><span class="sxs-lookup"><span data-stu-id="4403e-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="4403e-144">Alle Versionen können in die Kategorie schreiben.</span><span class="sxs-lookup"><span data-stu-id="4403e-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="4403e-145">Wenn CategoryOptions auf 1 festgelegt ist, wird globaler freigegebener Speicher verwendet, instanziierte Daten können jedoch wiederverwendet werden, wenn der Kategoriename die gleiche Länge wie die wiederverwendete Kategorie hat.</span><span class="sxs-lookup"><span data-stu-id="4403e-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="4403e-146">Die Einstellungen 0 und 1 können zu Speicherverlusten und dem Auffüllen des Leistungsindikatorspeichers führen.</span><span class="sxs-lookup"><span data-stu-id="4403e-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4403e-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4403e-147">Example</span></span>  
 <span data-ttu-id="4403e-148">Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass PerfCounter.dll auf den Registrierungseintrag CategoryOptions verweisen soll, um zu bestimmen, ob kategoriespezifischer freigegebener Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4403e-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4403e-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4403e-149">See also</span></span>

- [<span data-ttu-id="4403e-150">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4403e-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4403e-151">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="4403e-151">Configuration File Schema</span></span>](../index.md)

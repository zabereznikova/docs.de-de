---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178241"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="104e7-102">\<forcePerformanceCounterUniqueSharedMemoryReads>-Element</span><span class="sxs-lookup"><span data-stu-id="104e7-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>

<span data-ttu-id="104e7-103">Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="104e7-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="104e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="104e7-104">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="104e7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="104e7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="104e7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="104e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="104e7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="104e7-107">Attributes</span></span>  
  
|<span data-ttu-id="104e7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="104e7-108">Attribute</span></span>|<span data-ttu-id="104e7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="104e7-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="104e7-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="104e7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="104e7-111">Gibt an, ob PerfCounter.dll die Registrierungs Einstellung categoryoptions verwendet, um zu bestimmen, ob Leistungsdaten aus dem kategoriespezifischen gemeinsam genutzten oder globalen Arbeitsspeicher geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="104e7-111">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="104e7-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="104e7-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="104e7-113">Wert</span><span class="sxs-lookup"><span data-stu-id="104e7-113">Value</span></span>|<span data-ttu-id="104e7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="104e7-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="104e7-115">PerfCounter.dll verwendet nicht die Registrierungs Einstellung categoryoptions, dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="104e7-115">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="104e7-116">PerfCounter.dll verwendet die Registrierungs Einstellung categoryoptions.</span><span class="sxs-lookup"><span data-stu-id="104e7-116">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="104e7-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="104e7-117">Child Elements</span></span>  

 <span data-ttu-id="104e7-118">Keine</span><span class="sxs-lookup"><span data-stu-id="104e7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="104e7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="104e7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="104e7-120">Element</span><span class="sxs-lookup"><span data-stu-id="104e7-120">Element</span></span>|<span data-ttu-id="104e7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="104e7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="104e7-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="104e7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="104e7-123">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="104e7-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="104e7-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="104e7-124">Remarks</span></span>  

 <span data-ttu-id="104e7-125">In Versionen der .NET Framework vor dem .NET Framework 4 entsprach die Version von PerfCounter.dll, die geladen wurde, der Laufzeit, die in den Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="104e7-125">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="104e7-126">Wenn auf einem Computer sowohl der .NET Framework Version 1,1 als auch .NET Framework 2,0 installiert war, würde eine .NET Framework 1,1-Anwendung die .NET Framework 1,1-Version PerfCounter.dll laden.</span><span class="sxs-lookup"><span data-stu-id="104e7-126">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="104e7-127">Ab .NET Framework 4 wird die neueste installierte Version von PerfCounter.dll geladen.</span><span class="sxs-lookup"><span data-stu-id="104e7-127">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="104e7-128">Dies bedeutet, dass eine .NET Framework 1,1-Anwendung die .NET Framework 4-Version von PerfCounter.dll lädt, wenn die .NET Framework 4 auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="104e7-128">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="104e7-129">Ab der .NET Framework 4 prüft PerfCounter.dll bei der Nutzung von Leistungsindikatoren den Registrierungs Eintrag categoryoptions für jeden Anbieter, um zu bestimmen, ob er aus dem kategoriespezifischen freigegebenen Arbeitsspeicher oder dem globalen gemeinsam genutzten Speicher lesen soll.</span><span class="sxs-lookup"><span data-stu-id="104e7-129">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="104e7-130">Der .NET Framework 1,1 PerfCounter.dll liest diesen Registrierungs Eintrag nicht, da er keinen kategoriespezifischen freigegebenen Arbeitsspeicher kennt. Er liest immer aus dem globalen gemeinsam genutzten Speicher.</span><span class="sxs-lookup"><span data-stu-id="104e7-130">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="104e7-131">Aus Gründen der Abwärtskompatibilität überprüft der .NET Framework 4-PerfCounter.dll den Registrierungs Eintrag categoryoptions nicht, wenn er in einer .NET Framework 1,1-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="104e7-131">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="104e7-132">Es verwendet einfach den globalen gemeinsam genutzten Speicher, genau wie die .NET Framework 1,1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="104e7-132">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="104e7-133">Sie können jedoch die .NET Framework 4-PerfCounter.dll anweisen, die Registrierungs Einstellung durch Aktivieren des-Elements zu überprüfen `<forcePerformanceCounterUniqueSharedMemoryReads>` .</span><span class="sxs-lookup"><span data-stu-id="104e7-133">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="104e7-134">Das Aktivieren des `<forcePerformanceCounterUniqueSharedMemoryReads>` -Elements garantiert nicht, dass kategoriespezifischer gemeinsam genutzter Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="104e7-134">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="104e7-135">Wenn die Einstellung aktiviert ist, `true` bewirkt dies nur PerfCounter.dll, dass auf die Registrierungs Einstellung categoryoptions verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="104e7-135">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="104e7-136">Die Standardeinstellung für categoryoptions ist die Verwendung des kategoriespezifischen freigegebenen Speichers. Sie können jedoch categoryoptions ändern, um anzugeben, dass der globale gemeinsame Arbeitsspeicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="104e7-136">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="104e7-137">Der Registrierungsschlüssel, der die Einstellung categoryoptions enthält, ist HKEY_LOCAL_MACHINE \system\currentcontrolset\services \\<CategoryName \> \Performance.</span><span class="sxs-lookup"><span data-stu-id="104e7-137">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="104e7-138">Standardmäßig ist "categoryoptions" auf "3" festgelegt, was PerfCounter.dll anweist, kategoriespezifischen freigegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="104e7-138">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="104e7-139">Wenn categoryoptions auf 0 festgelegt ist, PerfCounter.dll den globalen gemeinsam genutzten Arbeitsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="104e7-139">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="104e7-140">Instanzdaten werden nur dann wieder verwendet, wenn der Name der Instanz, die erstellt wird, mit der Instanz identisch ist, die wieder verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="104e7-140">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="104e7-141">Alle Versionen können in die Kategorie schreiben.</span><span class="sxs-lookup"><span data-stu-id="104e7-141">All versions will be able to write to the category.</span></span> <span data-ttu-id="104e7-142">Wenn categoryoptions auf 1 festgelegt ist, wird der globale freigegebene Speicher verwendet, aber Instanzdaten können wieder verwendet werden, wenn der Kategoriename dieselbe Länge wie die wiederverwendbare Kategorie hat.</span><span class="sxs-lookup"><span data-stu-id="104e7-142">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="104e7-143">Die Einstellungen 0 und 1 können zu Speicher Verlusten und zum Auffüllen des Leistungs Zählers führen.</span><span class="sxs-lookup"><span data-stu-id="104e7-143">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="104e7-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="104e7-144">Example</span></span>  

 <span data-ttu-id="104e7-145">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass PerfCounter.dll auf den Registrierungs Eintrag categoryoptions verweisen soll, um zu bestimmen, ob der Kategoriespezifische freigegebene Speicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="104e7-145">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="104e7-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="104e7-146">See also</span></span>

- [<span data-ttu-id="104e7-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="104e7-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="104e7-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="104e7-148">Configuration File Schema</span></span>](../index.md)

---
title: '&lt;GcConcurrent&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 254b3be8f270a9186377b264094c919314efb27f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="11c85-102">&lt;GcConcurrent&gt; Element</span><span class="sxs-lookup"><span data-stu-id="11c85-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="11c85-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="11c85-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="11c85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="11c85-104">\<configuration></span></span>  
<span data-ttu-id="11c85-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="11c85-105">\<runtime></span></span>  
<span data-ttu-id="11c85-106">\<GcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="11c85-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c85-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="11c85-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11c85-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11c85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="11c85-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11c85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11c85-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="11c85-110">Attributes</span></span>  
  
|<span data-ttu-id="11c85-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="11c85-111">Attribute</span></span>|<span data-ttu-id="11c85-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11c85-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="11c85-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="11c85-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="11c85-114">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="11c85-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="11c85-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="11c85-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="11c85-116">Wert</span><span class="sxs-lookup"><span data-stu-id="11c85-116">Value</span></span>|<span data-ttu-id="11c85-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11c85-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="11c85-118">Die Garbage Collection wird nicht gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="11c85-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="11c85-119">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="11c85-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="11c85-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c85-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11c85-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11c85-121">Child Elements</span></span>  
 <span data-ttu-id="11c85-122">Keine</span><span class="sxs-lookup"><span data-stu-id="11c85-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11c85-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11c85-123">Parent Elements</span></span>  
  
|<span data-ttu-id="11c85-124">Element</span><span class="sxs-lookup"><span data-stu-id="11c85-124">Element</span></span>|<span data-ttu-id="11c85-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11c85-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="11c85-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="11c85-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="11c85-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="11c85-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c85-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11c85-128">Remarks</span></span>  
 <span data-ttu-id="11c85-129">Vor .NET Framework 4 unterstützt die Garbage Collection auf einer Arbeitsstation gleichzeitige Garbage Collection, bei der die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11c85-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="11c85-130">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt, bei der die Garbage Collection ebenfalls im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11c85-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="11c85-131">Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund für Garbage Collection auf dem Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11c85-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="11c85-132">Das `<gcConcurrent>`-Element steuert, ob die Runtime entweder gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund ausführt, sofern diese verfügbar ist, oder ob die Runtime die Garbage Collection im Vordergrund ausführt.</span><span class="sxs-lookup"><span data-stu-id="11c85-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="11c85-133">Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt.</span><span class="sxs-lookup"><span data-stu-id="11c85-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="11c85-134">Die Begriffe *gleichzeitige* und *Hintergrund* werden in der .NET Framework-Dokumentation synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="11c85-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="11c85-135">Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das `<gcConcurrent>`-Element wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11c85-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="11c85-136">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="11c85-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="11c85-137">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="11c85-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="11c85-138">Wenn Sie das `enabled`-Attribut des `<gcConcurrent>`-Elements auf `false` festlegen, verwendet die Runtime die nicht-parallele Garbage Collection, die für Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="11c85-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="11c85-139">Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="11c85-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="11c85-140">Gibt es eine `<gcConcurrentSetting>`-Einstellung in der Computerkonfigurationsdatei, legt diese den Standardwert für alle .NET Framework-Anwendungen fest.</span><span class="sxs-lookup"><span data-stu-id="11c85-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="11c85-141">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="11c85-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="11c85-142">Weitere Informationen zur gleichzeitigen und Garbagecollection im Hintergrund finden Sie im Abschnitt "gleichzeitige Garbagecollection" in der [Grundlagen der Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="11c85-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11c85-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11c85-143">Example</span></span>  
 <span data-ttu-id="11c85-144">Im folgenden Beispiel wird die gleichzeitige Garbage Collection aktiviert.</span><span class="sxs-lookup"><span data-stu-id="11c85-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11c85-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11c85-145">See Also</span></span>  
 [<span data-ttu-id="11c85-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="11c85-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="11c85-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="11c85-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="11c85-148">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="11c85-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)

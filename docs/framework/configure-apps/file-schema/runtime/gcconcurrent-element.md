---
title: <gcConcurrent>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2774c32b4ee3e67772f84d599ecc5dbeb6598b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252589"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="b6f78-102">\<gcConcurrent-> Element</span><span class="sxs-lookup"><span data-stu-id="b6f78-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="b6f78-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="b6f78-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6f78-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6f78-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6f78-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b6f78-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcConcurrent>**</span><span class="sxs-lookup"><span data-stu-id="b6f78-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcConcurrent>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="b6f78-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6f78-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6f78-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6f78-108">Attributes and elements</span></span>

<span data-ttu-id="b6f78-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6f78-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6f78-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6f78-110">Attributes</span></span>

|<span data-ttu-id="b6f78-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b6f78-111">Attribute</span></span>|<span data-ttu-id="b6f78-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6f78-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b6f78-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b6f78-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b6f78-114">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="b6f78-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="b6f78-115">enabled attribute</span></span>

|<span data-ttu-id="b6f78-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b6f78-116">Value</span></span>|<span data-ttu-id="b6f78-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6f78-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="b6f78-118">Wird Garbage Collection nicht gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="b6f78-119">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="b6f78-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b6f78-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b6f78-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6f78-121">Child elements</span></span>

<span data-ttu-id="b6f78-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b6f78-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b6f78-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6f78-123">Parent elements</span></span>

|<span data-ttu-id="b6f78-124">Element</span><span class="sxs-lookup"><span data-stu-id="b6f78-124">Element</span></span>|<span data-ttu-id="b6f78-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6f78-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b6f78-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b6f78-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b6f78-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6f78-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6f78-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6f78-128">Remarks</span></span>

<span data-ttu-id="b6f78-129">Vor .NET Framework 4 unterstützt die Garbage Collection auf einer Arbeitsstation gleichzeitige Garbage Collection, bei der die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6f78-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="b6f78-130">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt, bei der die Garbage Collection ebenfalls im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6f78-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="b6f78-131">Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund für Garbage Collection auf dem Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b6f78-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="b6f78-132">Das `<gcConcurrent>` -Element steuert, ob die Laufzeit entweder gleichzeitige oder Hintergrund Garbage Collection ausführt, wenn Sie verfügbar ist, oder ob Sie im Vordergrund Garbage Collection ausführt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="b6f78-133">So deaktivieren Sie Hintergrund Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b6f78-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="b6f78-134">Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b6f78-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="b6f78-135">Die Begriffe " *parallel* " und " *Background* " werden in der .NET Framework-Dokumentation austauschbar verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6f78-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="b6f78-136">Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das `<gcConcurrent>`-Element wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6f78-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="b6f78-137">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="b6f78-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="b6f78-138">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="b6f78-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="b6f78-139">Wenn Sie das `enabled`-Attribut des `<gcConcurrent>`-Elements auf `false` festlegen, verwendet die Runtime die nicht-parallele Garbage Collection, die für Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="b6f78-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="b6f78-140">Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="b6f78-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="b6f78-141">Wenn eine `<gcConcurrentSetting>` Einstellung in der Computer Konfigurationsdatei vorhanden ist, wird der Standardwert für alle .NET Framework Anwendungen definiert.</span><span class="sxs-lookup"><span data-stu-id="b6f78-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="b6f78-142">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="b6f78-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="b6f78-143">Weitere Informationen zu gleichzeitigen und Hintergrund Garbage Collection finden Sie im Abschnitt [gleichzeitige Garbage Collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) im Artikel [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .</span><span class="sxs-lookup"><span data-stu-id="b6f78-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="b6f78-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6f78-144">Example</span></span>

<span data-ttu-id="b6f78-145">Im folgenden Beispiel wird die parallele Garbage Collection aktiviert:</span><span class="sxs-lookup"><span data-stu-id="b6f78-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b6f78-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6f78-146">See also</span></span>

- [<span data-ttu-id="b6f78-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b6f78-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b6f78-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b6f78-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b6f78-149">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b6f78-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)

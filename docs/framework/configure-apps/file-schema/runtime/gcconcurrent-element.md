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
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674102"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="a1d79-102">\<GcConcurrent >-Element</span><span class="sxs-lookup"><span data-stu-id="a1d79-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="a1d79-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="a1d79-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="a1d79-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="a1d79-104">\<configuration>\\</span></span>
<span data-ttu-id="a1d79-105">\<runtime>\\</span><span class="sxs-lookup"><span data-stu-id="a1d79-105">\<runtime>\\</span></span>
<span data-ttu-id="a1d79-106">\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="a1d79-106">\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="a1d79-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1d79-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1d79-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1d79-108">Attributes and elements</span></span>

<span data-ttu-id="a1d79-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1d79-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1d79-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1d79-110">Attributes</span></span>

|<span data-ttu-id="a1d79-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1d79-111">Attribute</span></span>|<span data-ttu-id="a1d79-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1d79-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a1d79-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a1d79-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1d79-114">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="a1d79-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="a1d79-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a1d79-115">enabled attribute</span></span>

|<span data-ttu-id="a1d79-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a1d79-116">Value</span></span>|<span data-ttu-id="a1d79-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1d79-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a1d79-118">Garbagecollection nicht gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a1d79-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="a1d79-119">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1d79-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="a1d79-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a1d79-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a1d79-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1d79-121">Child elements</span></span>

<span data-ttu-id="a1d79-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a1d79-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a1d79-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1d79-123">Parent elements</span></span>

|<span data-ttu-id="a1d79-124">Element</span><span class="sxs-lookup"><span data-stu-id="a1d79-124">Element</span></span>|<span data-ttu-id="a1d79-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1d79-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a1d79-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a1d79-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a1d79-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a1d79-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a1d79-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1d79-128">Remarks</span></span>

<span data-ttu-id="a1d79-129">Vor .NET Framework 4 unterstützt die Garbage Collection auf einer Arbeitsstation gleichzeitige Garbage Collection, bei der die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1d79-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a1d79-130">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt, bei der die Garbage Collection ebenfalls im Hintergrund auf einem separaten Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1d79-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a1d79-131">Ab .NET Framework 4.5 ist die Garbage Collection im Hintergrund für Garbage Collection auf dem Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1d79-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="a1d79-132">Die `<gcConcurrent>` -Element steuert, ob die Runtime entweder gleichzeitige führt "oder" background Garbagecollection, sofern diese verfügbar ist oder ob er die Garbagecollection im Vordergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1d79-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="a1d79-133">So deaktivieren Sie die Garbagecollection im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="a1d79-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="a1d79-134">Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a1d79-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="a1d79-135">Die Begriffe *gleichzeitige* und *Hintergrund* werden in der .NET Framework-Dokumentation synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1d79-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="a1d79-136">Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das `<gcConcurrent>`-Element wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1d79-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="a1d79-137">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1d79-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="a1d79-138">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1d79-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="a1d79-139">Wenn Sie das `enabled`-Attribut des `<gcConcurrent>`-Elements auf `false` festlegen, verwendet die Runtime die nicht-parallele Garbage Collection, die für Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1d79-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="a1d79-140">Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="a1d79-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="a1d79-141">Es ist ein `<gcConcurrentSetting>` festlegen, in der Konfigurationsdatei des Computers, den Standardwert für alle .NET Framework-Anwendungen definiert.</span><span class="sxs-lookup"><span data-stu-id="a1d79-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="a1d79-142">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="a1d79-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="a1d79-143">Weitere Informationen zur gleichzeitigen und Garbagecollection im Hintergrund finden Sie in der [gleichzeitige Garbagecollection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) im Abschnitt der [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) Artikel.</span><span class="sxs-lookup"><span data-stu-id="a1d79-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="a1d79-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1d79-144">Example</span></span>

<span data-ttu-id="a1d79-145">Im folgenden Beispiel wird die gleichzeitige Garbagecollection:</span><span class="sxs-lookup"><span data-stu-id="a1d79-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a1d79-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d79-146">See also</span></span>

- [<span data-ttu-id="a1d79-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a1d79-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a1d79-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a1d79-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a1d79-149">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a1d79-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)

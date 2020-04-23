---
title: gcConcurrent-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102917"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="89f43-102">\<gcConcurrent>-Element</span><span class="sxs-lookup"><span data-stu-id="89f43-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="89f43-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="89f43-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="89f43-104">[\<Konfiguration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89f43-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="89f43-105">&nbsp;&nbsp;[\<Laufzeit>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="89f43-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="89f43-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="89f43-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="89f43-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="89f43-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89f43-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89f43-108">Attributes and elements</span></span>

<span data-ttu-id="89f43-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89f43-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="89f43-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="89f43-110">Attributes</span></span>

|<span data-ttu-id="89f43-111">attribute</span><span class="sxs-lookup"><span data-stu-id="89f43-111">Attribute</span></span>|<span data-ttu-id="89f43-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89f43-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="89f43-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="89f43-113">Required attribute.</span></span><br /><br /><span data-ttu-id="89f43-114">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="89f43-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="89f43-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="89f43-115">enabled attribute</span></span>

|<span data-ttu-id="89f43-116">Wert</span><span class="sxs-lookup"><span data-stu-id="89f43-116">Value</span></span>|<span data-ttu-id="89f43-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89f43-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="89f43-118">Führt die Garbage Collection nicht gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="89f43-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="89f43-119">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89f43-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="89f43-120">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="89f43-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="89f43-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89f43-121">Child elements</span></span>

<span data-ttu-id="89f43-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="89f43-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="89f43-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89f43-123">Parent elements</span></span>

|<span data-ttu-id="89f43-124">Element</span><span class="sxs-lookup"><span data-stu-id="89f43-124">Element</span></span>|<span data-ttu-id="89f43-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89f43-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="89f43-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="89f43-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="89f43-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="89f43-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89f43-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89f43-128">Remarks</span></span>

<span data-ttu-id="89f43-129">Vor .NET Framework 4 unterstützte die Garbage Collection auf Arbeitsstation die gleichzeitige Garbage Collection, die die Garbage Collection im Hintergrund in einem separaten Thread durchführte.</span><span class="sxs-lookup"><span data-stu-id="89f43-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="89f43-130">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch Background-GC ersetzt, das auch die Garbage Collection im Hintergrund für einen separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="89f43-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="89f43-131">Ab .NET Framework 4.5 wurde die Hintergrundsammlung in der Servergarbage-Auflistung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89f43-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="89f43-132">Das **gcConcurrent-Element** steuert, ob die Laufzeit entweder gleichzeitige oder Hintergrund-Garbage Collection durchführt, ob sie verfügbar ist, oder ob sie die Garbage Collection im Vordergrund ausführt.</span><span class="sxs-lookup"><span data-stu-id="89f43-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="89f43-133">So deaktivieren Sie die Hintergrund-Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="89f43-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="89f43-134">Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt.</span><span class="sxs-lookup"><span data-stu-id="89f43-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="89f43-135">Die Begriffe *gleichzeitig* und *Hintergrund* werden in der .NET Framework-Dokumentation austauschbar verwendet.</span><span class="sxs-lookup"><span data-stu-id="89f43-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="89f43-136">Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das **gcConcurrent-Element,** wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89f43-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="89f43-137">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="89f43-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="89f43-138">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="89f43-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="89f43-139">Wenn Sie `enabled` das Attribut des **gcConcurrent-Elements** auf `false`festlegen, verwendet die Laufzeit eine nicht gleichzeitige Garbage Collection, die für den Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="89f43-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="89f43-140">Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund:</span><span class="sxs-lookup"><span data-stu-id="89f43-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="89f43-141">Wenn die Computerkonfigurationsdatei eine **gcConcurrentSetting-Einstellung** enthält, wird der Standardwert für alle .NET Framework-Anwendungen definiert.</span><span class="sxs-lookup"><span data-stu-id="89f43-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="89f43-142">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="89f43-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="89f43-143">Weitere Informationen zur gleichzeitigen Garbage Collection und zur Hintergrundgarbageauflistung finden Sie unter [Hintergrund-Garbage Collection](../../../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="89f43-143">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="89f43-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89f43-144">Example</span></span>

<span data-ttu-id="89f43-145">Im folgenden Beispiel wird die Garbage Collection im Hintergrund aktiviert:</span><span class="sxs-lookup"><span data-stu-id="89f43-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="89f43-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89f43-146">See also</span></span>

- [<span data-ttu-id="89f43-147">Laufzeiteinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="89f43-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="89f43-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="89f43-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="89f43-149">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="89f43-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)

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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102917"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="2f9f3-102">\<gcConcurrent>-Element</span><span class="sxs-lookup"><span data-stu-id="2f9f3-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="2f9f3-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a><span data-ttu-id="2f9f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f9f3-104">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f9f3-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f9f3-105">Attributes and elements</span></span>

<span data-ttu-id="2f9f3-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f9f3-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f9f3-107">Attributes</span></span>

|<span data-ttu-id="2f9f3-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2f9f3-108">Attribute</span></span>|<span data-ttu-id="2f9f3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f9f3-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2f9f3-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-110">Required attribute.</span></span><br /><br /><span data-ttu-id="2f9f3-111">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-111">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="2f9f3-112">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="2f9f3-112">enabled attribute</span></span>

|<span data-ttu-id="2f9f3-113">Wert</span><span class="sxs-lookup"><span data-stu-id="2f9f3-113">Value</span></span>|<span data-ttu-id="2f9f3-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f9f3-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2f9f3-115">Wird Garbage Collection nicht gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-115">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="2f9f3-116">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-116">Runs garbage collection concurrently.</span></span> <span data-ttu-id="2f9f3-117">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-117">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2f9f3-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f9f3-118">Child elements</span></span>

<span data-ttu-id="2f9f3-119">Keine</span><span class="sxs-lookup"><span data-stu-id="2f9f3-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f9f3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f9f3-120">Parent elements</span></span>

|<span data-ttu-id="2f9f3-121">Element</span><span class="sxs-lookup"><span data-stu-id="2f9f3-121">Element</span></span>|<span data-ttu-id="2f9f3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f9f3-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2f9f3-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2f9f3-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2f9f3-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2f9f3-125">Remarks</span></span>

<span data-ttu-id="2f9f3-126">Vor .NET Framework 4 Garbage Collection die Arbeitsstation gleichzeitige Garbage Collection unterstützt, die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-126">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="2f9f3-127">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch den Background-GC ersetzt, der auch Garbage Collection im Hintergrund in einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-127">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="2f9f3-128">Ab .NET Framework 4,5 wurde die Hintergrund Sammlung in Server Garbage Collection verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-128">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="2f9f3-129">Das **gcConcurrent** -Element steuert, ob die Laufzeit entweder gleichzeitige oder Hintergrund Garbage Collection ausführt, wenn Sie verfügbar ist, oder ob Sie im Vordergrund Garbage Collection ausführt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-129">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="2f9f3-130">So deaktivieren Sie Hintergrund Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="2f9f3-130">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="2f9f3-131">Beginnend mit .NET Framework 4 wird die gleichzeitige Garbage Collection durch Hintergrund Garbage Collection ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-131">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="2f9f3-132">Die Begriffe " *parallel* " und " *Background* " werden in der .NET Framework-Dokumentation austauschbar verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-132">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="2f9f3-133">Um die Hintergrund Garbage Collection zu deaktivieren, verwenden Sie das **gcConcurrent** -Element, wie in diesem Artikel erläutert.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-133">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="2f9f3-134">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-134">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="2f9f3-135">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-135">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="2f9f3-136">Wenn Sie das- `enabled` Attribut des **gcConcurrent** -Elements auf festlegen `false` , verwendet die Common Language Runtime nicht gleichzeitige Garbage Collection, die für den Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-136">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="2f9f3-137">Mit der folgenden Konfigurationsdatei wird die Hintergrund Garbage Collection deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="2f9f3-137">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="2f9f3-138">Wenn eine **gcconcurrentsetting** -Einstellung in der Computer Konfigurationsdatei vorhanden ist, wird der Standardwert für alle .NET Framework Anwendungen definiert.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-138">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="2f9f3-139">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="2f9f3-139">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="2f9f3-140">Weitere Informationen zu gleichzeitigen und Hintergrund Garbage Collection finden Sie unter [Hintergrund Garbage Collection](../../../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="2f9f3-140">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="2f9f3-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f9f3-141">Example</span></span>

<span data-ttu-id="2f9f3-142">Im folgenden Beispiel werden Hintergrund Garbage Collection aktiviert:</span><span class="sxs-lookup"><span data-stu-id="2f9f3-142">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2f9f3-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f9f3-143">See also</span></span>

- [<span data-ttu-id="2f9f3-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2f9f3-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2f9f3-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2f9f3-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2f9f3-146">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="2f9f3-146">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)

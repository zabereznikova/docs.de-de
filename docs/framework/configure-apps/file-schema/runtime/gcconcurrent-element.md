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
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969235"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="a3d87-102">\<gcConcurrent-> Element</span><span class="sxs-lookup"><span data-stu-id="a3d87-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="a3d87-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="a3d87-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3d87-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="a3d87-105">&nbsp;&nbsp;[\<Lauf Zeit >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3d87-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="a3d87-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="a3d87-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="a3d87-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3d87-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a3d87-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3d87-108">Attributes and elements</span></span>

<span data-ttu-id="a3d87-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3d87-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a3d87-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3d87-110">Attributes</span></span>

|<span data-ttu-id="a3d87-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3d87-111">Attribute</span></span>|<span data-ttu-id="a3d87-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3d87-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a3d87-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a3d87-113">Required attribute.</span></span><br /><br /><span data-ttu-id="a3d87-114">Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="a3d87-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="a3d87-115">enabled attribute</span></span>

|<span data-ttu-id="a3d87-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a3d87-116">Value</span></span>|<span data-ttu-id="a3d87-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3d87-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a3d87-118">Wird Garbage Collection nicht gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="a3d87-119">Die Garbage Collection wird gleichzeitig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="a3d87-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a3d87-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a3d87-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3d87-121">Child elements</span></span>

<span data-ttu-id="a3d87-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a3d87-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a3d87-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3d87-123">Parent elements</span></span>

|<span data-ttu-id="a3d87-124">Element</span><span class="sxs-lookup"><span data-stu-id="a3d87-124">Element</span></span>|<span data-ttu-id="a3d87-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3d87-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a3d87-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a3d87-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a3d87-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a3d87-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a3d87-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3d87-128">Remarks</span></span>

<span data-ttu-id="a3d87-129">Vor .NET Framework 4 Garbage Collection die Arbeitsstation gleichzeitige Garbage Collection unterstützt, die Garbage Collection im Hintergrund auf einem separaten Thread ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="a3d87-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a3d87-130">In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch den Background-GC ersetzt, der auch Garbage Collection im Hintergrund in einem separaten Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a3d87-131">Ab .NET Framework 4,5 wurde die Hintergrund Sammlung in Server Garbage Collection verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3d87-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="a3d87-132">Das **gcConcurrent** -Element steuert, ob die Laufzeit entweder gleichzeitige oder Hintergrund Garbage Collection ausführt, wenn Sie verfügbar ist, oder ob Sie im Vordergrund Garbage Collection ausführt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="a3d87-133">So deaktivieren Sie Hintergrund Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a3d87-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="a3d87-134">Beginnend mit .NET Framework 4 wird die gleichzeitige Garbage Collection durch Hintergrund Garbage Collection ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a3d87-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="a3d87-135">Die Begriffe " *parallel* " und " *Background* " werden in der .NET Framework-Dokumentation austauschbar verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3d87-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="a3d87-136">Um die Hintergrund Garbage Collection zu deaktivieren, verwenden Sie das **gcConcurrent** -Element, wie in diesem Artikel erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3d87-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="a3d87-137">Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3d87-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="a3d87-138">Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3d87-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="a3d87-139">Wenn Sie das `enabled`-Attribut des **gcConcurrent** -Elements auf `false`festlegen, verwendet die Common Language Runtime nicht gleichzeitige Garbage Collection, das für den Durchsatz optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3d87-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="a3d87-140">Mit der folgenden Konfigurationsdatei wird die Hintergrund Garbage Collection deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="a3d87-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="a3d87-141">Wenn eine **gcconcurrentsetting** -Einstellung in der Computer Konfigurationsdatei vorhanden ist, wird der Standardwert für alle .NET Framework Anwendungen definiert.</span><span class="sxs-lookup"><span data-stu-id="a3d87-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="a3d87-142">Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="a3d87-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="a3d87-143">Weitere Informationen zu gleichzeitigen und Hintergrund Garbage Collection finden Sie in den Abschnitten [parallele Garbage Collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Hintergrund](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)Arbeitsstations Garbage Collection und [Hintergrund Server Garbage Collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) im Artikel [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .</span><span class="sxs-lookup"><span data-stu-id="a3d87-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="a3d87-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3d87-144">Example</span></span>

<span data-ttu-id="a3d87-145">Im folgenden Beispiel werden Hintergrund Garbage Collection aktiviert:</span><span class="sxs-lookup"><span data-stu-id="a3d87-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a3d87-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3d87-146">See also</span></span>

- [<span data-ttu-id="a3d87-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a3d87-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a3d87-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a3d87-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a3d87-149">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a3d87-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)

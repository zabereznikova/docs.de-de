---
title: Gcheapaffinitizemask-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73978420"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="90322-102">\<GCHeapAffinitizeMask>-Element</span><span class="sxs-lookup"><span data-stu-id="90322-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="90322-103">Definiert die Affinität zwischen GC-Heaps und einzelnen Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="90322-103">Defines the affinity between GC heaps and individual processors.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a><span data-ttu-id="90322-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90322-104">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90322-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90322-105">Attributes and elements</span></span>

<span data-ttu-id="90322-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90322-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="90322-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="90322-107">Attributes</span></span>

|<span data-ttu-id="90322-108">attribute</span><span class="sxs-lookup"><span data-stu-id="90322-108">Attribute</span></span>|<span data-ttu-id="90322-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90322-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="90322-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="90322-110">Required attribute.</span></span><br /><br /><span data-ttu-id="90322-111">Gibt die Affinität zwischen GC-Heaps und einzelnen Prozessoren an.</span><span class="sxs-lookup"><span data-stu-id="90322-111">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="90322-112">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="90322-112">enabled attribute</span></span>

|<span data-ttu-id="90322-113">Wert</span><span class="sxs-lookup"><span data-stu-id="90322-113">Value</span></span>|<span data-ttu-id="90322-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90322-114">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="90322-115">Ein Dezimalwert, der eine Bitmaske bildet, die die Affinität zwischen Server-GC-Heaps und einzelnen Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="90322-115">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="90322-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90322-116">Child elements</span></span>

<span data-ttu-id="90322-117">Keine</span><span class="sxs-lookup"><span data-stu-id="90322-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90322-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90322-118">Parent elements</span></span>

|<span data-ttu-id="90322-119">Element</span><span class="sxs-lookup"><span data-stu-id="90322-119">Element</span></span>|<span data-ttu-id="90322-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90322-120">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="90322-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="90322-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="90322-122">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="90322-122">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90322-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90322-123">Remarks</span></span>

<span data-ttu-id="90322-124">Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="90322-124">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="90322-125">Beginnend mit .NET Framework 4.6.2 können Sie das **gcheapaffinitizemask** -Element verwenden, um die Affinität zwischen Server-GC-Heaps und-Prozessoren zu steuern, wenn die Anzahl der Heaps durch das **gcheapcount** -Element begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="90322-125">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="90322-126">**Gcheapaffinitizemask** wird in der Regel zusammen mit zwei anderen Flags verwendet:</span><span class="sxs-lookup"><span data-stu-id="90322-126">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="90322-127">[Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="90322-127">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="90322-128">Das- `enabled` Attribut des [gcnoaffinitize](gcnoaffinitize-element.md) -Elements muss `false` (sein Standardwert) für die zu verwendende **gcheapaffinitizemask** -Einstellung sein.</span><span class="sxs-lookup"><span data-stu-id="90322-128">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="90322-129">[Gcheapcount](gcheapcount-element.md): schränkt die Anzahl von Heaps ein, die vom Prozess für Server-GC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90322-129">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="90322-130">Standardmäßig gibt es für jeden Prozessor einen Heap.</span><span class="sxs-lookup"><span data-stu-id="90322-130">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="90322-131">**nnnn** ist eine Bitmaske, die als Dezimalwert ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="90322-131">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="90322-132">Bit 0 von Byte 0 stellt den Prozessor 0 dar, Bit 1 von Byte 0 steht für Prozessor 1 usw.</span><span class="sxs-lookup"><span data-stu-id="90322-132">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="90322-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="90322-133">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="90322-134">Der Wert 1023 ist 0x3ff oder 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="90322-134">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="90322-135">Der Prozess verwendet 10 Prozessoren von Prozessor 0 bis Prozessor 9.</span><span class="sxs-lookup"><span data-stu-id="90322-135">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="90322-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90322-136">Example</span></span>

<span data-ttu-id="90322-137">Das folgende Beispiel gibt an, dass eine Anwendung Server-GC mit 10 Heaps/Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="90322-137">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="90322-138">Da Sie nicht möchten, dass sich diese Heaps mit Heaps von anderen Anwendungen auf dem System überlappen, verwenden Sie **gcheapaffinitizemask** , um anzugeben, dass der Prozess die CPUs 0 bis 9 verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="90322-138">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="90322-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90322-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="90322-140">Gcnoaffinitize-Element</span><span class="sxs-lookup"><span data-stu-id="90322-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="90322-141">Gcheapcount-Element</span><span class="sxs-lookup"><span data-stu-id="90322-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="90322-142">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="90322-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="90322-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="90322-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="90322-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="90322-144">Configuration File Schema</span></span>](../index.md)

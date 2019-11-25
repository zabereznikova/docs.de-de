---
title: Gcheapaffinitizemask-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978420"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="566a3-102">\<gcheapaffinitizemask > Element</span><span class="sxs-lookup"><span data-stu-id="566a3-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="566a3-103">Definiert die Affinität zwischen GC-Heaps und einzelnen Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="566a3-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="566a3-104">\<Konfigurations > </span><span class="sxs-lookup"><span data-stu-id="566a3-104">\<configuration></span></span>\
<span data-ttu-id="566a3-105">&nbsp;&nbsp;\<Lauf Zeit > </span><span class="sxs-lookup"><span data-stu-id="566a3-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="566a3-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcheapaffinitizemask ></span><span class="sxs-lookup"><span data-stu-id="566a3-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="566a3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="566a3-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="566a3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="566a3-108">Attributes and elements</span></span>

<span data-ttu-id="566a3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="566a3-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="566a3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="566a3-110">Attributes</span></span>

|<span data-ttu-id="566a3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="566a3-111">Attribute</span></span>|<span data-ttu-id="566a3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="566a3-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="566a3-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="566a3-113">Required attribute.</span></span><br /><br /><span data-ttu-id="566a3-114">Gibt die Affinität zwischen GC-Heaps und einzelnen Prozessoren an.</span><span class="sxs-lookup"><span data-stu-id="566a3-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="566a3-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="566a3-115">enabled attribute</span></span>

|<span data-ttu-id="566a3-116">Wert</span><span class="sxs-lookup"><span data-stu-id="566a3-116">Value</span></span>|<span data-ttu-id="566a3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="566a3-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="566a3-118">Ein Dezimalwert, der eine Bitmaske bildet, die die Affinität zwischen Server-GC-Heaps und einzelnen Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="566a3-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="566a3-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="566a3-119">Child elements</span></span>

<span data-ttu-id="566a3-120">Keine</span><span class="sxs-lookup"><span data-stu-id="566a3-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="566a3-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="566a3-121">Parent elements</span></span>

|<span data-ttu-id="566a3-122">Element</span><span class="sxs-lookup"><span data-stu-id="566a3-122">Element</span></span>|<span data-ttu-id="566a3-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="566a3-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="566a3-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="566a3-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="566a3-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="566a3-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="566a3-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="566a3-126">Remarks</span></span>

<span data-ttu-id="566a3-127">Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="566a3-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="566a3-128">Beginnend mit .NET Framework 4.6.2 können Sie das **gcheapaffinitizemask** -Element verwenden, um die Affinität zwischen Server-GC-Heaps und-Prozessoren zu steuern, wenn die Anzahl der Heaps durch das **gcheapcount** -Element begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="566a3-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="566a3-129">**Gcheapaffinitizemask** wird in der Regel zusammen mit zwei anderen Flags verwendet:</span><span class="sxs-lookup"><span data-stu-id="566a3-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="566a3-130">[Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="566a3-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="566a3-131">Das `enabled`-Attribut des [gcnoaffinitize](gcnoaffinitize-element.md) -Elements muss `false` (sein Standardwert) für die zu verwendende **gcheapaffinitizemask** -Einstellung sein.</span><span class="sxs-lookup"><span data-stu-id="566a3-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="566a3-132">[Gcheapcount](gcheapcount-element.md): schränkt die Anzahl von Heaps ein, die vom Prozess für Server-GC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="566a3-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="566a3-133">Standardmäßig gibt es für jeden Prozessor einen Heap.</span><span class="sxs-lookup"><span data-stu-id="566a3-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="566a3-134">**nnnn** ist eine Bitmaske, die als Dezimalwert ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="566a3-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="566a3-135">Bit 0 von Byte 0 stellt den Prozessor 0 dar, Bit 1 von Byte 0 steht für Prozessor 1 usw.</span><span class="sxs-lookup"><span data-stu-id="566a3-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="566a3-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="566a3-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="566a3-137">Der Wert 1023 ist 0x3ff oder 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="566a3-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="566a3-138">Der Prozess verwendet 10 Prozessoren von Prozessor 0 bis Prozessor 9.</span><span class="sxs-lookup"><span data-stu-id="566a3-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="566a3-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="566a3-139">Example</span></span>

<span data-ttu-id="566a3-140">Das folgende Beispiel gibt an, dass eine Anwendung Server-GC mit 10 Heaps/Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="566a3-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="566a3-141">Da Sie nicht möchten, dass sich diese Heaps mit Heaps von anderen Anwendungen auf dem System überlappen, verwenden Sie **gcheapaffinitizemask** , um anzugeben, dass der Prozess die CPUs 0 bis 9 verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="566a3-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="566a3-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="566a3-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="566a3-143">Gcnoaffinitize-Element</span><span class="sxs-lookup"><span data-stu-id="566a3-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="566a3-144">Gcheapcount-Element</span><span class="sxs-lookup"><span data-stu-id="566a3-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="566a3-145">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="566a3-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="566a3-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="566a3-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="566a3-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="566a3-147">Configuration File Schema</span></span>](../index.md)

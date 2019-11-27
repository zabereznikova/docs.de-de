---
title: Gcheapcount-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283072"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="93150-102">\<gcheapcount > Element</span><span class="sxs-lookup"><span data-stu-id="93150-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="93150-103">Gibt die Anzahl von Heaps/Threads an, die für Server Garbage Collection verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="93150-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

<span data-ttu-id="93150-104">\<Konfigurations > </span><span class="sxs-lookup"><span data-stu-id="93150-104">\<configuration></span></span>\
<span data-ttu-id="93150-105">&nbsp;&nbsp;\<Lauf Zeit > </span><span class="sxs-lookup"><span data-stu-id="93150-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="93150-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcheapcount ></span><span class="sxs-lookup"><span data-stu-id="93150-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount></span></span>

## <a name="syntax"></a><span data-ttu-id="93150-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="93150-107">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93150-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="93150-108">Attributes and elements</span></span>

<span data-ttu-id="93150-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93150-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="93150-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="93150-110">Attributes</span></span>

|<span data-ttu-id="93150-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="93150-111">Attribute</span></span>|<span data-ttu-id="93150-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93150-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="93150-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="93150-113">Required attribute.</span></span><br /><br /><span data-ttu-id="93150-114">Gibt die Anzahl von Heaps an, die für Server Garbage Collection verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="93150-114">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="93150-115">Die tatsächliche Anzahl von Heaps ist die Mindestanzahl der von Ihnen angegebenen Heaps und der Anzahl der Prozessoren, die Ihr Prozess verwenden darf.</span><span class="sxs-lookup"><span data-stu-id="93150-115">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="93150-116">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="93150-116">enabled attribute</span></span>

|<span data-ttu-id="93150-117">Wert</span><span class="sxs-lookup"><span data-stu-id="93150-117">Value</span></span>|<span data-ttu-id="93150-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93150-118">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="93150-119">Die Anzahl von Heaps, die für Server-GC verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="93150-119">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="93150-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93150-120">Child elements</span></span>

<span data-ttu-id="93150-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="93150-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93150-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93150-122">Parent elements</span></span>

|<span data-ttu-id="93150-123">Element</span><span class="sxs-lookup"><span data-stu-id="93150-123">Element</span></span>|<span data-ttu-id="93150-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93150-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="93150-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="93150-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="93150-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="93150-126">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93150-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93150-127">Remarks</span></span>

<span data-ttu-id="93150-128">Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="93150-128">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="93150-129">Ab .NET Framework 4.6.2 können Sie das **gcheapcount** -Element verwenden, um die Anzahl von Heaps einzuschränken, die von der Anwendung für die Server-GC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93150-129">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="93150-130">Das Einschränken der Anzahl von Heaps, die für Server GC verwendet werden, ist besonders nützlich für Systeme, die mehrere Instanzen einer Serveranwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="93150-130">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="93150-131">**Gcheapcount** wird in der Regel zusammen mit zwei anderen Flags verwendet:</span><span class="sxs-lookup"><span data-stu-id="93150-131">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="93150-132">[Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="93150-132">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="93150-133">[Gcheapaffinitizemask](gcheapaffinitizemask-element.md): steuert die Affinität von GC-Threads/Heaps mit CPUs.</span><span class="sxs-lookup"><span data-stu-id="93150-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="93150-134">Wenn **gcheapcount** festgelegt und **gcnoaffininitize** deaktiviert ist (Standardeinstellung), gibt es eine Affinität zwischen den *NN* -GC-Threads/Heaps und den ersten *NN* -Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="93150-134">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="93150-135">Sie können das **gcheapaffinitizemask** -Element verwenden, um anzugeben, welche Prozessoren von den Server-GC-Heaps des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93150-135">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="93150-136">Andernfalls überschneidet sich die Prozessorauslastung, wenn mehrere Server Prozesse auf einem System ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="93150-136">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="93150-137">Wenn **gcheapcount** festgelegt und **gcnoaffininitize** aktiviert ist, schränkt der Garbage Collector die Anzahl der Prozessoren ein, die für die Server-GC verwendet werden, aber keine GC-Heaps und-Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="93150-137">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="93150-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93150-138">Example</span></span>

<span data-ttu-id="93150-139">Das folgende Beispiel gibt an, dass eine Anwendung Server-GC mit 10 Heaps/Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="93150-139">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="93150-140">Da Sie nicht möchten, dass sich diese Heaps mit Heaps von anderen Anwendungen auf dem System überlappen, verwenden Sie **gcheapaffinitizemask** , um anzugeben, dass der Prozess die CPUs 0 bis 9 verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="93150-140">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="93150-141">Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 beschränkt.</span><span class="sxs-lookup"><span data-stu-id="93150-141">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="93150-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93150-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="93150-143">Gcnoaffinitize-Element</span><span class="sxs-lookup"><span data-stu-id="93150-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="93150-144">Gcheapaffinitizemask-Element</span><span class="sxs-lookup"><span data-stu-id="93150-144">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="93150-145">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="93150-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="93150-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="93150-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="93150-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="93150-147">Configuration File Schema</span></span>](../index.md)

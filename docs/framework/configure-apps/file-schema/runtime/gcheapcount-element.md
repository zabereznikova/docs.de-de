---
title: Gcheapcount-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283072"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="3bb9c-102">\<GCHeapCount>-Element</span><span class="sxs-lookup"><span data-stu-id="3bb9c-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="3bb9c-103">Gibt die Anzahl von Heaps/Threads an, die für Server Garbage Collection verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="3bb9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bb9c-104">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3bb9c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb9c-105">Attributes and elements</span></span>

<span data-ttu-id="3bb9c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3bb9c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3bb9c-107">Attributes</span></span>

|<span data-ttu-id="3bb9c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3bb9c-108">Attribute</span></span>|<span data-ttu-id="3bb9c-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3bb9c-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="3bb9c-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-110">Required attribute.</span></span><br /><br /><span data-ttu-id="3bb9c-111">Gibt die Anzahl von Heaps an, die für Server Garbage Collection verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-111">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="3bb9c-112">Die tatsächliche Anzahl von Heaps ist die Mindestanzahl der von Ihnen angegebenen Heaps und der Anzahl der Prozessoren, die Ihr Prozess verwenden darf.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-112">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="3bb9c-113">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="3bb9c-113">enabled attribute</span></span>

|<span data-ttu-id="3bb9c-114">Wert</span><span class="sxs-lookup"><span data-stu-id="3bb9c-114">Value</span></span>|<span data-ttu-id="3bb9c-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3bb9c-115">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="3bb9c-116">Die Anzahl von Heaps, die für Server-GC verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-116">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3bb9c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb9c-117">Child elements</span></span>

<span data-ttu-id="3bb9c-118">Keine</span><span class="sxs-lookup"><span data-stu-id="3bb9c-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3bb9c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb9c-119">Parent elements</span></span>

|<span data-ttu-id="3bb9c-120">Element</span><span class="sxs-lookup"><span data-stu-id="3bb9c-120">Element</span></span>|<span data-ttu-id="3bb9c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bb9c-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3bb9c-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="3bb9c-123">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3bb9c-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3bb9c-124">Remarks</span></span>

<span data-ttu-id="3bb9c-125">Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="3bb9c-126">Ab .NET Framework 4.6.2 können Sie das **gcheapcount** -Element verwenden, um die Anzahl von Heaps einzuschränken, die von der Anwendung für die Server-GC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="3bb9c-127">Das Einschränken der Anzahl von Heaps, die für Server GC verwendet werden, ist besonders nützlich für Systeme, die mehrere Instanzen einer Serveranwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-127">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="3bb9c-128">**Gcheapcount** wird in der Regel zusammen mit zwei anderen Flags verwendet:</span><span class="sxs-lookup"><span data-stu-id="3bb9c-128">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="3bb9c-129">[Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-129">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="3bb9c-130">[Gcheapaffinitizemask](gcheapaffinitizemask-element.md): steuert die Affinität von GC-Threads/Heaps mit CPUs.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="3bb9c-131">Wenn **gcheapcount** festgelegt und **gcnoaffininitize** deaktiviert ist (Standardeinstellung), gibt es eine Affinität zwischen den *NN* -GC-Threads/Heaps und den ersten *NN* -Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-131">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="3bb9c-132">Sie können das **gcheapaffinitizemask** -Element verwenden, um anzugeben, welche Prozessoren von den Server-GC-Heaps des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-132">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="3bb9c-133">Andernfalls überschneidet sich die Prozessorauslastung, wenn mehrere Server Prozesse auf einem System ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-133">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="3bb9c-134">Wenn **gcheapcount** festgelegt und **gcnoaffininitize** aktiviert ist, schränkt der Garbage Collector die Anzahl der Prozessoren ein, die für die Server-GC verwendet werden, aber keine GC-Heaps und-Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-134">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="3bb9c-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bb9c-135">Example</span></span>

<span data-ttu-id="3bb9c-136">Das folgende Beispiel gibt an, dass eine Anwendung Server-GC mit 10 Heaps/Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-136">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="3bb9c-137">Da Sie nicht möchten, dass sich diese Heaps mit Heaps von anderen Anwendungen auf dem System überlappen, verwenden Sie **gcheapaffinitizemask** , um anzugeben, dass der Prozess die CPUs 0 bis 9 verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-137">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="3bb9c-138">Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 beschränkt.</span><span class="sxs-lookup"><span data-stu-id="3bb9c-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3bb9c-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bb9c-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3bb9c-140">Gcnoaffinitize-Element</span><span class="sxs-lookup"><span data-stu-id="3bb9c-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="3bb9c-141">Gcheapaffinitizemask-Element</span><span class="sxs-lookup"><span data-stu-id="3bb9c-141">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="3bb9c-142">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="3bb9c-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="3bb9c-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="3bb9c-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3bb9c-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="3bb9c-144">Configuration File Schema</span></span>](../index.md)

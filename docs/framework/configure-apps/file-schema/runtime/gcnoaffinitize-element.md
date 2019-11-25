---
title: Gcnoaffinitize-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978414"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="00dba-102">\<gcnoaffinitize > Element</span><span class="sxs-lookup"><span data-stu-id="00dba-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="00dba-103">Gibt an, ob Server-GC-Threads mit CPUs verknüpft werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="00dba-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

<span data-ttu-id="00dba-104">\<Konfigurations > </span><span class="sxs-lookup"><span data-stu-id="00dba-104">\<configuration></span></span>\
<span data-ttu-id="00dba-105">&nbsp;&nbsp;\<Lauf Zeit > </span><span class="sxs-lookup"><span data-stu-id="00dba-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="00dba-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcnoaffinitize ></span><span class="sxs-lookup"><span data-stu-id="00dba-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize></span></span>

## <a name="syntax"></a><span data-ttu-id="00dba-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="00dba-107">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00dba-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00dba-108">Attributes and elements</span></span>

<span data-ttu-id="00dba-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00dba-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="00dba-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="00dba-110">Attributes</span></span>

|<span data-ttu-id="00dba-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="00dba-111">Attribute</span></span>|<span data-ttu-id="00dba-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00dba-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="00dba-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="00dba-113">Required attribute.</span></span><br /><br /><span data-ttu-id="00dba-114">Gibt an, ob Server-GC-Threads/Heaps den auf dem Computer verfügbaren Prozessoren zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="00dba-114">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="00dba-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="00dba-115">enabled attribute</span></span>

|<span data-ttu-id="00dba-116">Wert</span><span class="sxs-lookup"><span data-stu-id="00dba-116">Value</span></span>|<span data-ttu-id="00dba-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00dba-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="00dba-118">Affininitialisiert Server-GC-Threads mit CPUs.</span><span class="sxs-lookup"><span data-stu-id="00dba-118">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="00dba-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="00dba-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="00dba-120">Fügt Server-GC-Threads nicht mit CPUs zu.</span><span class="sxs-lookup"><span data-stu-id="00dba-120">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="00dba-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00dba-121">Child elements</span></span>

<span data-ttu-id="00dba-122">Keine</span><span class="sxs-lookup"><span data-stu-id="00dba-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00dba-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00dba-123">Parent elements</span></span>

|<span data-ttu-id="00dba-124">Element</span><span class="sxs-lookup"><span data-stu-id="00dba-124">Element</span></span>|<span data-ttu-id="00dba-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00dba-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="00dba-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="00dba-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="00dba-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="00dba-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="00dba-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00dba-128">Remarks</span></span>

<span data-ttu-id="00dba-129">Standardmäßig sind Server-GC-Threads mit ihren jeweiligen CPUs hart miteinander initialisiert.</span><span class="sxs-lookup"><span data-stu-id="00dba-129">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="00dba-130">Jeder verfügbare Prozessor des Systems verfügt über einen eigenen GC-Heap und-Thread.</span><span class="sxs-lookup"><span data-stu-id="00dba-130">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="00dba-131">Dies ist in der Regel die bevorzugte Einstellung, da Sie die Cache Verwendung optimiert.</span><span class="sxs-lookup"><span data-stu-id="00dba-131">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="00dba-132">Beginnend mit .NET Framework 4.6.2, indem das `enabled`-Attribut des **gcnoaffinitize** -Elements auf `false`festgelegt wird, können Sie angeben, dass Server-GC-Threads und-CPUs nicht eng gekoppelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00dba-132">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `false`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="00dba-133">Sie können das **gcnoaffinitize** -Konfigurationselement allein angeben, um Server-GC-Threads nicht mit CPUs zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="00dba-133">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="00dba-134">Sie können es auch zusammen mit dem [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Heaps und-Threads zu steuern, die von einer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00dba-134">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="00dba-135">Wenn das `enabled`-Attribut des **gcnoaffinitize** -Elements `false` (der Standardwert) ist, können Sie auch das [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Threads und Heaps anzugeben, zusammen mit dem [gcheapaffinitizemask](gcheapaffinitizemask-element.md) -Element, um die Prozessoren anzugeben, denen die GC-Threads und Heaps zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="00dba-135">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="00dba-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00dba-136">Example</span></span>

<span data-ttu-id="00dba-137">Im folgenden Beispiel werden Server-GC-Threads nicht hart zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="00dba-137">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="00dba-138">Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 begrenzt:</span><span class="sxs-lookup"><span data-stu-id="00dba-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="00dba-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00dba-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="00dba-140">Gcheapaffinitizemask-Element</span><span class="sxs-lookup"><span data-stu-id="00dba-140">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="00dba-141">Gcheapcount-Element</span><span class="sxs-lookup"><span data-stu-id="00dba-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="00dba-142">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="00dba-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="00dba-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="00dba-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00dba-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="00dba-144">Configuration File Schema</span></span>](../index.md)

---
title: Gcnoaffinitize-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84004737"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="ddb18-102">\<GCNoAffinitize>-Element</span><span class="sxs-lookup"><span data-stu-id="ddb18-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="ddb18-103">Gibt an, ob Server-GC-Threads mit CPUs verknüpft werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ddb18-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="ddb18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddb18-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ddb18-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb18-105">Attributes and elements</span></span>

<span data-ttu-id="ddb18-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddb18-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ddb18-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ddb18-107">Attributes</span></span>

|<span data-ttu-id="ddb18-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ddb18-108">Attribute</span></span>|<span data-ttu-id="ddb18-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ddb18-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ddb18-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ddb18-110">Required attribute.</span></span><br /><br /><span data-ttu-id="ddb18-111">Gibt an, ob Server-GC-Threads/Heaps den auf dem Computer verfügbaren Prozessoren zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb18-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="ddb18-112">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="ddb18-112">enabled attribute</span></span>

|<span data-ttu-id="ddb18-113">Wert</span><span class="sxs-lookup"><span data-stu-id="ddb18-113">Value</span></span>|<span data-ttu-id="ddb18-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ddb18-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="ddb18-115">Affininitialisiert Server-GC-Threads mit CPUs.</span><span class="sxs-lookup"><span data-stu-id="ddb18-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="ddb18-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ddb18-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="ddb18-117">Fügt Server-GC-Threads nicht mit CPUs zu.</span><span class="sxs-lookup"><span data-stu-id="ddb18-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ddb18-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb18-118">Child elements</span></span>

<span data-ttu-id="ddb18-119">Keine</span><span class="sxs-lookup"><span data-stu-id="ddb18-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ddb18-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb18-120">Parent elements</span></span>

|<span data-ttu-id="ddb18-121">Element</span><span class="sxs-lookup"><span data-stu-id="ddb18-121">Element</span></span>|<span data-ttu-id="ddb18-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddb18-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ddb18-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ddb18-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ddb18-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ddb18-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddb18-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ddb18-125">Remarks</span></span>

<span data-ttu-id="ddb18-126">Standardmäßig sind Server-GC-Threads mit ihren jeweiligen CPUs hart miteinander initialisiert.</span><span class="sxs-lookup"><span data-stu-id="ddb18-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="ddb18-127">Jeder verfügbare Prozessor des Systems verfügt über einen eigenen GC-Heap und-Thread.</span><span class="sxs-lookup"><span data-stu-id="ddb18-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="ddb18-128">Dies ist in der Regel die bevorzugte Einstellung, da Sie die Cache Verwendung optimiert.</span><span class="sxs-lookup"><span data-stu-id="ddb18-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="ddb18-129">Beginnend mit .NET Framework 4.6.2, indem das-Attribut des **gcnoaffinitize** -Elements auf festgelegt wird `enabled` `true` , können Sie angeben, dass Server-GC-Threads und-CPUs nicht eng gekoppelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ddb18-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="ddb18-130">Sie können das **gcnoaffinitize** -Konfigurationselement allein angeben, um Server-GC-Threads nicht mit CPUs zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="ddb18-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="ddb18-131">Sie können es auch zusammen mit dem [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Heaps und-Threads zu steuern, die von einer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb18-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="ddb18-132">Wenn das- `enabled` Attribut des **gcnoaffinitize** -Elements `false` (dessen Standardwert) ist, können Sie auch das [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Threads und Heaps anzugeben, zusammen mit dem [gcheapaffinitizemask](gcheapaffinitizemask-element.md) -Element, um die Prozessoren anzugeben, denen die GC-Threads und Heaps zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb18-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="ddb18-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddb18-133">Example</span></span>

<span data-ttu-id="ddb18-134">Im folgenden Beispiel werden Server-GC-Threads nicht hart zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="ddb18-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="ddb18-135">Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 begrenzt:</span><span class="sxs-lookup"><span data-stu-id="ddb18-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ddb18-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddb18-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ddb18-137">Gcheapaffinitizemask-Element</span><span class="sxs-lookup"><span data-stu-id="ddb18-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="ddb18-138">Gcheapcount-Element</span><span class="sxs-lookup"><span data-stu-id="ddb18-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="ddb18-139">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="ddb18-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="ddb18-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ddb18-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ddb18-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ddb18-141">Configuration File Schema</span></span>](../index.md)

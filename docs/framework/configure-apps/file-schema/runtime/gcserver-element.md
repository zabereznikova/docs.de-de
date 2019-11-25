---
title: gcserver-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968950"
---
# <a name="gcserver-element"></a><span data-ttu-id="aa208-102">\<gcserver >-Element</span><span class="sxs-lookup"><span data-stu-id="aa208-102">\<gcServer> element</span></span>

<span data-ttu-id="aa208-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="aa208-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="aa208-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa208-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="aa208-105">&nbsp;&nbsp;[\<Lauf Zeit >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa208-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="aa208-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcserver ></span><span class="sxs-lookup"><span data-stu-id="aa208-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="aa208-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa208-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa208-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa208-108">Attributes and elements</span></span>

<span data-ttu-id="aa208-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa208-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa208-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa208-110">Attributes</span></span>

|<span data-ttu-id="aa208-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="aa208-111">Attribute</span></span>|<span data-ttu-id="aa208-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa208-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="aa208-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="aa208-113">Required attribute.</span></span><br /><br /><span data-ttu-id="aa208-114">Gibt an, ob die Runtime die Garbage Collection auf dem Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="aa208-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="aa208-115">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="aa208-115">enabled attribute</span></span>

|<span data-ttu-id="aa208-116">Wert</span><span class="sxs-lookup"><span data-stu-id="aa208-116">Value</span></span>|<span data-ttu-id="aa208-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa208-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="aa208-118">Die Garbage Collection wird nicht auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa208-118">Does not run server garbage collection.</span></span> <span data-ttu-id="aa208-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="aa208-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="aa208-120">Die Garbage Collection wird auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa208-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="aa208-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa208-121">Child elements</span></span>

<span data-ttu-id="aa208-122">Keine</span><span class="sxs-lookup"><span data-stu-id="aa208-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aa208-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa208-123">Parent elements</span></span>

|<span data-ttu-id="aa208-124">Element</span><span class="sxs-lookup"><span data-stu-id="aa208-124">Element</span></span>|<span data-ttu-id="aa208-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa208-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="aa208-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="aa208-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="aa208-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="aa208-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa208-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa208-128">Remarks</span></span>

<span data-ttu-id="aa208-129">Die Common Language Runtime (CLR) unterstützt zwei Arten der Garbage Collection: die Garbage Collection auf der Arbeitsstation, die auf allen Systemen verfügbar ist, und die Garbage Collection auf dem Server, die auf Systemen mit mehreren Prozessoren verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="aa208-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="aa208-130">Verwenden Sie das **gcserver** -Element, um den Typ des Garbage Collection zu steuern, den die CLR ausführt.</span><span class="sxs-lookup"><span data-stu-id="aa208-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="aa208-131">Mithilfe der <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>-Eigenschaft können Sie bestimmen, ob die Garbage Collection auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="aa208-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="aa208-132">Für Computer mit einem Prozessor stellt die Garbage Collection auf der Arbeitsstation (Standardeinstellung) in der Regel die schnellste Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="aa208-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="aa208-133">Auf Computern mit zwei Prozessoren kann die Arbeitsstation- oder die Serveroption verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa208-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="aa208-134">Sind mehr als zwei Prozessoren vorhanden, stellt die Garbage Collection auf dem Server in der Regel die schnellste Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="aa208-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="aa208-135">In den meisten Fällen deaktivieren Multiprozessor-Serversysteme die Server-GC und verwenden stattdessen die Arbeitsstations-GC, wenn viele Instanzen einer Server-App auf dem gleichen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa208-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="aa208-136">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden. Wenn es in der Computerkonfigurationsdatei enthalten ist, wird es ignoriert.</span><span class="sxs-lookup"><span data-stu-id="aa208-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="aa208-137">In .NET Framework 4 und früheren Versionen ist die gleichzeitige Garbage Collection nicht verfügbar, wenn die Garbage Collection auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="aa208-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="aa208-138">Beginnend mit dem .NET Framework 4,5 ist der Server Garbage Collection gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="aa208-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="aa208-139">Um nicht gleichzeitige Server Garbage Collection zu verwenden, legen Sie das **gcserver** -Element auf `true` und das [gcConcurrent-Element](gcconcurrent-element.md) auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="aa208-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="aa208-140">Ab .NET Framework 4.6.2 können Sie auch die folgenden Elemente verwenden, um Server GC zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="aa208-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="aa208-141">[Gcnoaffinitize](gcnoaffinitize-element.md): gibt an, ob zwischen Server-GC-Heaps und Prozessoren eine Affinität besteht.</span><span class="sxs-lookup"><span data-stu-id="aa208-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="aa208-142">Standardmäßig ist für jeden Prozessor ein Server-GC-Heap vorhanden.</span><span class="sxs-lookup"><span data-stu-id="aa208-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="aa208-143">[Gcheapcount](gcheapcount-element.md): schränkt die Anzahl von Heaps ein, die von einem Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa208-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="aa208-144">[Gcheapaffinitizemask](gcheapaffinitizemask-element.md): definiert die Affinität zwischen den verfügbaren Server-GC-Heaps und einzelnen Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="aa208-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="aa208-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa208-145">Example</span></span>

<span data-ttu-id="aa208-146">Im folgenden Beispiel wird die Server Garbage Collection aktiviert:</span><span class="sxs-lookup"><span data-stu-id="aa208-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="aa208-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa208-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aa208-148">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="aa208-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="aa208-149">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="aa208-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="aa208-150">So deaktivieren Sie die parallele Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="aa208-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)

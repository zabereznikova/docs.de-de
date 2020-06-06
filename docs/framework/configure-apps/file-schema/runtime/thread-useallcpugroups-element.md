---
title: <Thread_UseAllCpuGroups>-Element
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115407"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="cddc6-102">\<Thread_UseAllCpuGroups>-Element</span><span class="sxs-lookup"><span data-stu-id="cddc6-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="cddc6-103">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cddc6-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="cddc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cddc6-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cddc6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cddc6-105">Attributes and Elements</span></span>

<span data-ttu-id="cddc6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cddc6-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cddc6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="cddc6-107">Attributes</span></span>

|<span data-ttu-id="cddc6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="cddc6-108">Attribute</span></span>|<span data-ttu-id="cddc6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cddc6-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cddc6-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cddc6-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="cddc6-111">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cddc6-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="cddc6-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="cddc6-112">enabled Attribute</span></span>

|<span data-ttu-id="cddc6-113">Wert</span><span class="sxs-lookup"><span data-stu-id="cddc6-113">Value</span></span>|<span data-ttu-id="cddc6-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cddc6-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="cddc6-115">Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU-Gruppen verteilt.</span><span class="sxs-lookup"><span data-stu-id="cddc6-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="cddc6-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="cddc6-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="cddc6-117">Die Laufzeit verteilt verwaltete Threads auf mehrere CPU-Gruppen, wenn der Computer über mehrere CPU-Gruppen verfügt und das- [\<GCCpuGroup>](gccpugroup-element.md) Element aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cddc6-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cddc6-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cddc6-118">Child Elements</span></span>

<span data-ttu-id="cddc6-119">Keine</span><span class="sxs-lookup"><span data-stu-id="cddc6-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cddc6-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cddc6-120">Parent Elements</span></span>

|<span data-ttu-id="cddc6-121">Element</span><span class="sxs-lookup"><span data-stu-id="cddc6-121">Element</span></span>|<span data-ttu-id="cddc6-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cddc6-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cddc6-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cddc6-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cddc6-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cddc6-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cddc6-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cddc6-125">Remarks</span></span>

<span data-ttu-id="cddc6-126">Wenn ein Computer über mehrere CPU-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU-Gruppen zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="cddc6-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="cddc6-127">Um dieses Feature verwenden zu können, müssen Sie auch das- [\<GCCpuGroup>](gccpugroup-element.md) Element aktivieren, das Garbage Collection auf alle CPU-Gruppen erweitert und beim Erstellen und Ausgleichen von Heaps alle Kerne berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="cddc6-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="cddc6-128">Zum Aktivieren des- [\<GCCpuGroup>](gccpugroup-element.md) Elements muss das-Element aktiviert werden [\<gcServer>](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="cddc6-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="cddc6-129">Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="cddc6-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="cddc6-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cddc6-130">Example</span></span>

<span data-ttu-id="cddc6-131">Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU-Gruppen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cddc6-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cddc6-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cddc6-132">See also</span></span>

- [<span data-ttu-id="cddc6-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="cddc6-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cddc6-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="cddc6-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cddc6-135">\<GCCpuGroup>Gewisses</span><span class="sxs-lookup"><span data-stu-id="cddc6-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)

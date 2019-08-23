---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56b23b6d5fca6d0527d509c9b6a6fc6dd82336
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920781"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="f2d3e-102">\<Gccpugroup-> Element</span><span class="sxs-lookup"><span data-stu-id="f2d3e-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="f2d3e-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="f2d3e-104">\<Konfigurations > </span><span class="sxs-lookup"><span data-stu-id="f2d3e-104">\<configuration></span></span>\
<span data-ttu-id="f2d3e-105">\<Lauf Zeit > </span><span class="sxs-lookup"><span data-stu-id="f2d3e-105">\<runtime></span></span>\
<span data-ttu-id="f2d3e-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="f2d3e-106">\<GCCpuGroup></span></span>

## <a name="syntax"></a><span data-ttu-id="f2d3e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2d3e-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2d3e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d3e-108">Attributes and Elements</span></span>

<span data-ttu-id="f2d3e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2d3e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2d3e-110">Attributes</span></span>

|<span data-ttu-id="f2d3e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2d3e-111">Attribute</span></span>|<span data-ttu-id="f2d3e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d3e-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f2d3e-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f2d3e-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f2d3e-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f2d3e-115">enabled Attribute</span></span>

|<span data-ttu-id="f2d3e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="f2d3e-116">Value</span></span>|<span data-ttu-id="f2d3e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d3e-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f2d3e-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="f2d3e-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="f2d3e-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f2d3e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d3e-121">Child Elements</span></span>

<span data-ttu-id="f2d3e-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f2d3e-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2d3e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d3e-123">Parent Elements</span></span>

|<span data-ttu-id="f2d3e-124">Element</span><span class="sxs-lookup"><span data-stu-id="f2d3e-124">Element</span></span>|<span data-ttu-id="f2d3e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d3e-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f2d3e-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f2d3e-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2d3e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2d3e-128">Remarks</span></span>

<span data-ttu-id="f2d3e-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Server Garbage Collection aktiviert ist (siehe das [ \<>-Element von gcserver](gcserver-element.md) ), erweitert dieses Element Garbage Collection auf alle CPU-Gruppen und übernimmt alle Kerne beim Erstellen von und. Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="f2d3e-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="f2d3e-131">Damit die Laufzeit Benutzerthreads über alle CPU-Gruppen verteilen kann, müssen Sie auch das [ \<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) -Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="f2d3e-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2d3e-132">Example</span></span>

<span data-ttu-id="f2d3e-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f2d3e-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f2d3e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d3e-134">See also</span></span>

- [<span data-ttu-id="f2d3e-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f2d3e-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f2d3e-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f2d3e-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f2d3e-137">So deaktivieren Sie die parallele Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="f2d3e-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="f2d3e-138">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="f2d3e-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

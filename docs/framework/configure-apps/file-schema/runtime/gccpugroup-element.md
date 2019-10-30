---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: 352890519c1a227d664d877c3123866e5e4e1657
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116830"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="c6cbb-102">\<gccpugroup >-Element</span><span class="sxs-lookup"><span data-stu-id="c6cbb-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="c6cbb-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="c6cbb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6cbb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6cbb-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="c6cbb-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c6cbb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gccpugroup >**</span><span class="sxs-lookup"><span data-stu-id="c6cbb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c6cbb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6cbb-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c6cbb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c6cbb-108">Attributes and Elements</span></span>

<span data-ttu-id="c6cbb-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c6cbb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c6cbb-110">Attributes</span></span>

|<span data-ttu-id="c6cbb-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c6cbb-111">Attribute</span></span>|<span data-ttu-id="c6cbb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6cbb-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c6cbb-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6cbb-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="c6cbb-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c6cbb-115">enabled Attribute</span></span>

|<span data-ttu-id="c6cbb-116">Wert</span><span class="sxs-lookup"><span data-stu-id="c6cbb-116">Value</span></span>|<span data-ttu-id="c6cbb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6cbb-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="c6cbb-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="c6cbb-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="c6cbb-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c6cbb-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6cbb-121">Child Elements</span></span>

<span data-ttu-id="c6cbb-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c6cbb-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c6cbb-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6cbb-123">Parent Elements</span></span>

|<span data-ttu-id="c6cbb-124">Element</span><span class="sxs-lookup"><span data-stu-id="c6cbb-124">Element</span></span>|<span data-ttu-id="c6cbb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6cbb-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c6cbb-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c6cbb-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c6cbb-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6cbb-128">Remarks</span></span>

<span data-ttu-id="c6cbb-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Server Garbage Collection aktiviert ist (siehe das [\<gcserver >](gcserver-element.md) -Element), erweitert das Aktivieren dieses Elements Garbage Collection auf alle CPU-Gruppen und übernimmt beim Erstellen von und alle Kerne. Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="c6cbb-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="c6cbb-131">Damit die Laufzeit Benutzerthreads über alle CPU-Gruppen verteilen kann, müssen Sie auch das [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) -Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="c6cbb-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6cbb-132">Example</span></span>

<span data-ttu-id="c6cbb-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c6cbb-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c6cbb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6cbb-134">See also</span></span>

- [<span data-ttu-id="c6cbb-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c6cbb-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c6cbb-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c6cbb-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c6cbb-137">So deaktivieren Sie die parallele Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c6cbb-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="c6cbb-138">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="c6cbb-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

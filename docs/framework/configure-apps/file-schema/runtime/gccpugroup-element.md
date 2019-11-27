---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430484"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="30dcb-102">\<gccpugroup >-Element</span><span class="sxs-lookup"><span data-stu-id="30dcb-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="30dcb-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="30dcb-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="30dcb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30dcb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30dcb-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="30dcb-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="30dcb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gccpugroup >**</span><span class="sxs-lookup"><span data-stu-id="30dcb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="30dcb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="30dcb-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30dcb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30dcb-108">Attributes and Elements</span></span>

<span data-ttu-id="30dcb-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30dcb-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="30dcb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="30dcb-110">Attributes</span></span>

|<span data-ttu-id="30dcb-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="30dcb-111">Attribute</span></span>|<span data-ttu-id="30dcb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30dcb-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="30dcb-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="30dcb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="30dcb-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="30dcb-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="30dcb-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="30dcb-115">enabled Attribute</span></span>

|<span data-ttu-id="30dcb-116">Wert</span><span class="sxs-lookup"><span data-stu-id="30dcb-116">Value</span></span>|<span data-ttu-id="30dcb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30dcb-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="30dcb-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="30dcb-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="30dcb-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="30dcb-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="30dcb-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="30dcb-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="30dcb-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30dcb-121">Child Elements</span></span>

<span data-ttu-id="30dcb-122">None.</span><span class="sxs-lookup"><span data-stu-id="30dcb-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="30dcb-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30dcb-123">Parent Elements</span></span>

|<span data-ttu-id="30dcb-124">Element</span><span class="sxs-lookup"><span data-stu-id="30dcb-124">Element</span></span>|<span data-ttu-id="30dcb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30dcb-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="30dcb-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="30dcb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="30dcb-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="30dcb-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="30dcb-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30dcb-128">Remarks</span></span>

<span data-ttu-id="30dcb-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Server Garbage Collection aktiviert ist (siehe das [\<gcserver >](gcserver-element.md) -Element), erweitert das Aktivieren dieses Elements Garbage Collection auf alle CPU-Gruppen und übernimmt beim Erstellen und Ausgleichen von Heaps alle Kerne.</span><span class="sxs-lookup"><span data-stu-id="30dcb-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="30dcb-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="30dcb-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="30dcb-131">Damit die Laufzeit Benutzerthreads über alle CPU-Gruppen hinweg verteilen kann, müssen Sie auch das [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) -Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="30dcb-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="30dcb-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30dcb-132">Example</span></span>

<span data-ttu-id="30dcb-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="30dcb-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="30dcb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30dcb-134">See also</span></span>

- [<span data-ttu-id="30dcb-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="30dcb-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="30dcb-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="30dcb-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="30dcb-137">So deaktivieren Sie die parallele Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="30dcb-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="30dcb-138">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="30dcb-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)

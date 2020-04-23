---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102891"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="2a078-102">\<GCCpuGroup> Element</span><span class="sxs-lookup"><span data-stu-id="2a078-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="2a078-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2a078-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="2a078-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a078-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a078-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a078-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2a078-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span><span class="sxs-lookup"><span data-stu-id="2a078-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2a078-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a078-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2a078-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2a078-108">Attributes and Elements</span></span>

<span data-ttu-id="2a078-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a078-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2a078-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a078-110">Attributes</span></span>

|<span data-ttu-id="2a078-111">attribute</span><span class="sxs-lookup"><span data-stu-id="2a078-111">Attribute</span></span>|<span data-ttu-id="2a078-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a078-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2a078-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2a078-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a078-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2a078-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="2a078-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="2a078-115">enabled Attribute</span></span>

|<span data-ttu-id="2a078-116">Wert</span><span class="sxs-lookup"><span data-stu-id="2a078-116">Value</span></span>|<span data-ttu-id="2a078-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a078-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2a078-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="2a078-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="2a078-119">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="2a078-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="2a078-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2a078-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2a078-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a078-121">Child Elements</span></span>

<span data-ttu-id="2a078-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="2a078-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2a078-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a078-123">Parent Elements</span></span>

|<span data-ttu-id="2a078-124">Element</span><span class="sxs-lookup"><span data-stu-id="2a078-124">Element</span></span>|<span data-ttu-id="2a078-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a078-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2a078-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2a078-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2a078-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2a078-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2a078-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2a078-128">Remarks</span></span>

<span data-ttu-id="2a078-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und die Garbage Collection des Servers aktiviert ist (siehe [ \<gcServer](gcserver-element.md)>-Element), erweitert dieses Element die Garbage Collection auf alle CPU-Gruppen und berücksichtigt alle Kerne beim Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="2a078-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="2a078-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="2a078-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="2a078-131">Damit die Laufzeit Benutzerthreads auf alle CPU-Gruppen verteilen [ \<](thread-useallcpugroups-element.md) kann, müssen Sie auch die Thread_UseAllCpuGroups>-Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2a078-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="2a078-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a078-132">Example</span></span>

<span data-ttu-id="2a078-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2a078-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2a078-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a078-134">See also</span></span>

- [<span data-ttu-id="2a078-135">Laufzeiteinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="2a078-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2a078-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2a078-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2a078-137">Deaktivieren der gleichzeitigen Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="2a078-137">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="2a078-138">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="2a078-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)

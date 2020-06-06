---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102891"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="c1789-102">\<GCCpuGroup>-Element</span><span class="sxs-lookup"><span data-stu-id="c1789-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="c1789-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c1789-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="c1789-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1789-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c1789-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1789-105">Attributes and Elements</span></span>

<span data-ttu-id="c1789-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1789-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c1789-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1789-107">Attributes</span></span>

|<span data-ttu-id="c1789-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c1789-108">Attribute</span></span>|<span data-ttu-id="c1789-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c1789-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c1789-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c1789-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1789-111">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c1789-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="c1789-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c1789-112">enabled Attribute</span></span>

|<span data-ttu-id="c1789-113">Wert</span><span class="sxs-lookup"><span data-stu-id="c1789-113">Value</span></span>|<span data-ttu-id="c1789-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c1789-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="c1789-115">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="c1789-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="c1789-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c1789-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="c1789-117">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1789-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c1789-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1789-118">Child Elements</span></span>

<span data-ttu-id="c1789-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c1789-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c1789-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1789-120">Parent Elements</span></span>

|<span data-ttu-id="c1789-121">Element</span><span class="sxs-lookup"><span data-stu-id="c1789-121">Element</span></span>|<span data-ttu-id="c1789-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1789-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c1789-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c1789-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c1789-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c1789-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c1789-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c1789-125">Remarks</span></span>

<span data-ttu-id="c1789-126">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Server Garbage Collection aktiviert ist (siehe das- [\<gcServer>](gcserver-element.md) Element), wird durch Aktivieren dieses Elements Garbage Collection auf alle CPU-Gruppen ausgedehnt und beim Erstellen und Ausgleichen von Heaps alle Kerne berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="c1789-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="c1789-127">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="c1789-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="c1789-128">Damit die Laufzeit Benutzerthreads über alle CPU-Gruppen verteilen kann, müssen Sie auch das- [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) Element aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c1789-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="c1789-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1789-129">Example</span></span>

<span data-ttu-id="c1789-130">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c1789-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c1789-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1789-131">See also</span></span>

- [<span data-ttu-id="c1789-132">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c1789-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c1789-133">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c1789-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c1789-134">Gleichzeitige Garbage Collection deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c1789-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="c1789-135">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="c1789-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)

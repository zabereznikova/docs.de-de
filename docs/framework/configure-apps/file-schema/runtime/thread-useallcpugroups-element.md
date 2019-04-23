---
title: <Thread_UseAllCpuGroups>-Element
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230836"
---
# <a name="threaduseallcpugroups-element"></a><span data-ttu-id="b1c70-102">\<Thread_UseAllCpuGroups >-Element</span><span class="sxs-lookup"><span data-stu-id="b1c70-102">\<Thread_UseAllCpuGroups> Element</span></span>
<span data-ttu-id="b1c70-103">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="b1c70-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="b1c70-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b1c70-104">\<configuration></span></span>  
<span data-ttu-id="b1c70-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b1c70-105">\<runtime></span></span>  
<span data-ttu-id="b1c70-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="b1c70-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c70-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1c70-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1c70-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c70-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b1c70-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1c70-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1c70-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1c70-110">Attributes</span></span>  
  
|<span data-ttu-id="b1c70-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b1c70-111">Attribute</span></span>|<span data-ttu-id="b1c70-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c70-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b1c70-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b1c70-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b1c70-114">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="b1c70-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b1c70-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="b1c70-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b1c70-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b1c70-116">Value</span></span>|<span data-ttu-id="b1c70-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c70-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b1c70-118">Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU-Gruppen verteilt.</span><span class="sxs-lookup"><span data-stu-id="b1c70-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="b1c70-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b1c70-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b1c70-120">Von der Laufzeit verteilt verwaltete Threads auf mehrere CPU-Gruppen, wenn der Computer über mehrere CPU-Gruppen verfügt und die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b1c70-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1c70-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c70-121">Child Elements</span></span>  
 <span data-ttu-id="b1c70-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b1c70-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1c70-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1c70-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b1c70-124">Element</span><span class="sxs-lookup"><span data-stu-id="b1c70-124">Element</span></span>|<span data-ttu-id="b1c70-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1c70-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b1c70-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b1c70-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b1c70-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b1c70-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1c70-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1c70-128">Remarks</span></span>  
 <span data-ttu-id="b1c70-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU-Gruppen zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="b1c70-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="b1c70-130">Um dieses Feature verwenden zu können, müssen Sie auch aktivieren die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element, das wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne berücksichtigt beim Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="b1c70-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="b1c70-131">Aktivieren der [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Elements erfordert das Aktivieren der [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="b1c70-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="b1c70-132">Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="b1c70-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1c70-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1c70-133">Example</span></span>  
 <span data-ttu-id="b1c70-134">Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU-Gruppen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b1c70-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1c70-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1c70-135">See also</span></span>

- [<span data-ttu-id="b1c70-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b1c70-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b1c70-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b1c70-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b1c70-138">\<GCCpuGroup >-Element</span><span class="sxs-lookup"><span data-stu-id="b1c70-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)

---
title: <Thread_UseAllCpuGroups>-Element
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704686"
---
# <a name="threaduseallcpugroups-element"></a><span data-ttu-id="14b43-102">\<Thread_UseAllCpuGroups >-Element</span><span class="sxs-lookup"><span data-stu-id="14b43-102">\<Thread_UseAllCpuGroups> Element</span></span>
<span data-ttu-id="14b43-103">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="14b43-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="14b43-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14b43-104">\<configuration></span></span>  
<span data-ttu-id="14b43-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="14b43-105">\<runtime></span></span>  
<span data-ttu-id="14b43-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="14b43-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b43-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="14b43-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14b43-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14b43-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14b43-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14b43-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14b43-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="14b43-110">Attributes</span></span>  
  
|<span data-ttu-id="14b43-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="14b43-111">Attribute</span></span>|<span data-ttu-id="14b43-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b43-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="14b43-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="14b43-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="14b43-114">Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="14b43-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="14b43-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="14b43-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="14b43-116">Wert</span><span class="sxs-lookup"><span data-stu-id="14b43-116">Value</span></span>|<span data-ttu-id="14b43-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b43-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="14b43-118">Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU-Gruppen verteilt.</span><span class="sxs-lookup"><span data-stu-id="14b43-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="14b43-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="14b43-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="14b43-120">Von der Laufzeit verteilt verwaltete Threads auf mehrere CPU-Gruppen, wenn der Computer über mehrere CPU-Gruppen verfügt und die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="14b43-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14b43-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14b43-121">Child Elements</span></span>  
 <span data-ttu-id="14b43-122">Keine</span><span class="sxs-lookup"><span data-stu-id="14b43-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14b43-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14b43-123">Parent Elements</span></span>  
  
|<span data-ttu-id="14b43-124">Element</span><span class="sxs-lookup"><span data-stu-id="14b43-124">Element</span></span>|<span data-ttu-id="14b43-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b43-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="14b43-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="14b43-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="14b43-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="14b43-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14b43-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14b43-128">Remarks</span></span>  
 <span data-ttu-id="14b43-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU-Gruppen zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="14b43-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="14b43-130">Um dieses Feature verwenden zu können, müssen Sie auch aktivieren die [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Element, das wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne berücksichtigt beim Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="14b43-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="14b43-131">Aktivieren der [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) -Elements erfordert das Aktivieren der [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="14b43-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="14b43-132">Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="14b43-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14b43-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14b43-133">Example</span></span>  
 <span data-ttu-id="14b43-134">Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU-Gruppen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="14b43-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14b43-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14b43-135">See also</span></span>

- [<span data-ttu-id="14b43-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="14b43-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="14b43-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="14b43-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="14b43-138">\<GCCpuGroup >-Element</span><span class="sxs-lookup"><span data-stu-id="14b43-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)

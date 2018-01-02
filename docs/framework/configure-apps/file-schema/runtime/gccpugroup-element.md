---
title: '&lt;GCCpuGroup&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 510896c6993008f30e7eacf2628ae4cceadea7e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="a2119-102">&lt;GCCpuGroup&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a2119-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="a2119-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a2119-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="a2119-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2119-104">\<configuration></span></span>  
<span data-ttu-id="a2119-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="a2119-105">\<runtime></span></span>  
<span data-ttu-id="a2119-106">\<GCCpuGroup ></span><span class="sxs-lookup"><span data-stu-id="a2119-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2119-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2119-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2119-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2119-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2119-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2119-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2119-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2119-110">Attributes</span></span>  
  
|<span data-ttu-id="a2119-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2119-111">Attribute</span></span>|<span data-ttu-id="a2119-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2119-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a2119-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a2119-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a2119-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a2119-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a2119-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a2119-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a2119-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a2119-116">Value</span></span>|<span data-ttu-id="a2119-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2119-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a2119-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="a2119-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="a2119-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a2119-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a2119-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2119-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2119-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2119-121">Child Elements</span></span>  
 <span data-ttu-id="a2119-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a2119-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2119-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2119-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a2119-124">Element</span><span class="sxs-lookup"><span data-stu-id="a2119-124">Element</span></span>|<span data-ttu-id="a2119-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2119-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a2119-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a2119-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a2119-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2119-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2119-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2119-128">Remarks</span></span>  
 <span data-ttu-id="a2119-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Garbagecollection auf dem Server aktiviert ist (siehe die [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element), aktivieren dieses Element wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne in Konto beim Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="a2119-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2119-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="a2119-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="a2119-131">Sie müssen auch aktivieren, um das Laufzeitmodul zum Verteilen von Benutzerthreads auf alle CPU-Gruppen zu aktivieren, die [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a2119-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2119-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2119-132">Example</span></span>  
 <span data-ttu-id="a2119-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a2119-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2119-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2119-134">See Also</span></span>  
 [<span data-ttu-id="a2119-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a2119-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a2119-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a2119-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a2119-137">Vorgehensweise: Deaktivieren der gleichzeitigen Garbagecollection</span><span class="sxs-lookup"><span data-stu-id="a2119-137">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="a2119-138">Arbeitsstation und Server Garbagecollection</span><span class="sxs-lookup"><span data-stu-id="a2119-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

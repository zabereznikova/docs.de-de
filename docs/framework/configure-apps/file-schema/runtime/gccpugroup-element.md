---
title: '&lt;GCCpuGroup&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4461667bdb47d410c857b4ac2c9dd268438a02f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744017"
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="3b8d4-102">&lt;GCCpuGroup&gt; Element</span><span class="sxs-lookup"><span data-stu-id="3b8d4-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="3b8d4-103">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="3b8d4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3b8d4-104">\<configuration></span></span>  
<span data-ttu-id="3b8d4-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="3b8d4-105">\<runtime></span></span>  
<span data-ttu-id="3b8d4-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="3b8d4-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8d4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b8d4-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b8d4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8d4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3b8d4-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b8d4-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3b8d4-110">Attributes</span></span>  
  
|<span data-ttu-id="3b8d4-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="3b8d4-111">Attribute</span></span>|<span data-ttu-id="3b8d4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8d4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3b8d4-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3b8d4-114">Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3b8d4-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="3b8d4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3b8d4-116">Wert</span><span class="sxs-lookup"><span data-stu-id="3b8d4-116">Value</span></span>|<span data-ttu-id="3b8d4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8d4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3b8d4-118">Garbage Collection unterstützt mehrere CPU-Gruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="3b8d4-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3b8d4-120">Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b8d4-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8d4-121">Child Elements</span></span>  
 <span data-ttu-id="3b8d4-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3b8d4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b8d4-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8d4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3b8d4-124">Element</span><span class="sxs-lookup"><span data-stu-id="3b8d4-124">Element</span></span>|<span data-ttu-id="3b8d4-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8d4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3b8d4-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3b8d4-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b8d4-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b8d4-128">Remarks</span></span>  
 <span data-ttu-id="3b8d4-129">Wenn ein Computer über mehrere CPU-Gruppen verfügt und Garbagecollection auf dem Server aktiviert ist (siehe die [ \<GcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) Element), aktivieren dieses Element wird die Garbagecollection auf alle CPU-Gruppen und alle Kerne in Konto beim Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b8d4-130">Dieses Element gilt nur für Garbage Collection-Threads.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="3b8d4-131">Sie müssen auch aktivieren, um das Laufzeitmodul zum Verteilen von Benutzerthreads auf alle CPU-Gruppen zu aktivieren, die [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b8d4-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b8d4-132">Example</span></span>  
 <span data-ttu-id="3b8d4-133">Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3b8d4-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b8d4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b8d4-134">See Also</span></span>  
 [<span data-ttu-id="3b8d4-135">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="3b8d4-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3b8d4-136">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="3b8d4-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3b8d4-137">Vorgehensweise: Deaktivieren der gleichzeitigen Garbagecollection</span><span class="sxs-lookup"><span data-stu-id="3b8d4-137">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="3b8d4-138">Arbeitsstation und Server Garbagecollection</span><span class="sxs-lookup"><span data-stu-id="3b8d4-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

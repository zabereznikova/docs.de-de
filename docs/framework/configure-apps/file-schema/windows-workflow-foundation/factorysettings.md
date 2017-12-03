---
title: '&lt;factorySettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0df9a6bd4da9131961e0ca35ab75109053b97c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltfactorysettingsgt"></a><span data-ttu-id="91619-102">&lt;factorySettings&gt;</span><span class="sxs-lookup"><span data-stu-id="91619-102">&lt;factorySettings&gt;</span></span>
<span data-ttu-id="91619-103">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="91619-103">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="91619-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="91619-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="91619-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="91619-105">\<behaviors></span></span>  
<span data-ttu-id="91619-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="91619-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="91619-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="91619-107">\<behavior></span></span>  
<span data-ttu-id="91619-108">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="91619-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="91619-109">\<FactorySettings ></span><span class="sxs-lookup"><span data-stu-id="91619-109">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91619-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="91619-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91619-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91619-111">Attributes and Elements</span></span>  
 <span data-ttu-id="91619-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91619-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91619-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="91619-113">Attributes</span></span>  
  
|<span data-ttu-id="91619-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="91619-114">Attribute</span></span>|<span data-ttu-id="91619-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91619-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91619-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="91619-116">idleTimeout</span></span>|<span data-ttu-id="91619-117">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="91619-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="91619-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="91619-118">leaseTimeout</span></span>|<span data-ttu-id="91619-119">Ein TimeSpan-Wert, der das Zeitintervall angibt, nach denen ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="91619-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="91619-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="91619-120">maxItemsInCache</span></span>|<span data-ttu-id="91619-121">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="91619-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91619-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91619-122">Child Elements</span></span>  
 <span data-ttu-id="91619-123">Keine</span><span class="sxs-lookup"><span data-stu-id="91619-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91619-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91619-124">Parent Elements</span></span>  
  
|<span data-ttu-id="91619-125">Element</span><span class="sxs-lookup"><span data-stu-id="91619-125">Element</span></span>|<span data-ttu-id="91619-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91619-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91619-127">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="91619-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="91619-128">Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91619-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91619-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91619-129">Remarks</span></span>  
 <span data-ttu-id="91619-130">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="91619-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="91619-131">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="91619-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="91619-132">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="91619-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="91619-133">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="91619-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="91619-134">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="91619-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="91619-135">zum Ändern der standardcachefreigabeebenen und Einstellungen für die Kanalfactory und den channelcache Zwischenspeichern finden Sie unter [ändern die Cachefreigabeebenen für Aktivitäten senden](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="91619-135"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91619-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91619-136">Example</span></span>  
 <span data-ttu-id="91619-137">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="91619-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="91619-138">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="91619-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="91619-139">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit cacheeinstellungen für die benutzerdefinierte Factory und den channelcache.</span><span class="sxs-lookup"><span data-stu-id="91619-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="91619-140">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="91619-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91619-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91619-141">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [<span data-ttu-id="91619-142">Ändern der Cachefreigabeebenen für Send-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="91619-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

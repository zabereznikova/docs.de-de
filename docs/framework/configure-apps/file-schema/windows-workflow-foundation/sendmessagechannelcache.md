---
title: '&lt;sendmessagechannelcache an&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d9d4fbfe06209806ab1be9887b2e26d1a11a8954
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltsendmessagechannelcachegt"></a><span data-ttu-id="35219-102">&lt;sendmessagechannelcache an&gt;</span><span class="sxs-lookup"><span data-stu-id="35219-102">&lt;sendMessageChannelCache&gt;</span></span>
<span data-ttu-id="35219-103">Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35219-103">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="35219-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="35219-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="35219-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="35219-105">\<behaviors></span></span>  
<span data-ttu-id="35219-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="35219-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="35219-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="35219-107">\<behavior></span></span>  
<span data-ttu-id="35219-108">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="35219-108">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35219-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="35219-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35219-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="35219-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35219-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35219-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35219-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="35219-112">Attributes</span></span>  
  
|<span data-ttu-id="35219-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="35219-113">Attribute</span></span>|<span data-ttu-id="35219-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35219-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35219-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="35219-115">allowUnsafeCaching</span></span>|<span data-ttu-id="35219-116">Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35219-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="35219-117">Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="35219-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="35219-118">Jedoch, wenn Sie aktivieren möchten Zwischenspeichern auf legen Sie diese Eigenschaft auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="35219-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35219-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35219-119">Child Elements</span></span>  
  
|<span data-ttu-id="35219-120">Element</span><span class="sxs-lookup"><span data-stu-id="35219-120">Element</span></span>|<span data-ttu-id="35219-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35219-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35219-122">\<ChannelSettings ></span><span class="sxs-lookup"><span data-stu-id="35219-122">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="35219-123">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="35219-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="35219-124">\<FactorySettings ></span><span class="sxs-lookup"><span data-stu-id="35219-124">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="35219-125">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="35219-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35219-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35219-126">Parent Elements</span></span>  
  
|<span data-ttu-id="35219-127">Element</span><span class="sxs-lookup"><span data-stu-id="35219-127">Element</span></span>|<span data-ttu-id="35219-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35219-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35219-129">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="35219-129">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="35219-130">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="35219-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35219-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35219-131">Remarks</span></span>  
 <span data-ttu-id="35219-132">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="35219-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="35219-133">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="35219-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="35219-134">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="35219-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="35219-135">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="35219-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="35219-136">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="35219-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="35219-137">zum Ändern der standardcachefreigabeebenen und Einstellungen für die Kanalfactory und den channelcache Zwischenspeichern finden Sie unter [ändern die Cachefreigabeebenen für Aktivitäten senden](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="35219-137"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35219-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35219-138">Example</span></span>  
 <span data-ttu-id="35219-139">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="35219-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="35219-140">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="35219-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="35219-141">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit cacheeinstellungen für die benutzerdefinierte Factory und den channelcache.</span><span class="sxs-lookup"><span data-stu-id="35219-141">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="35219-142">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="35219-142">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35219-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35219-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [<span data-ttu-id="35219-144">Ändern der Cachefreigabeebenen für Send-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="35219-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

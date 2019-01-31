---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 1c8e381aa81655e8e3246e783ee7da45623d83ca
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289249"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="2fa44-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="2fa44-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="2fa44-102">Ein Dienstverhalten, das es, die cachefreigabeebenen Ebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden ermöglicht-messagingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="2fa44-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="2fa44-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2fa44-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2fa44-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2fa44-104">\<behaviors></span></span>  
<span data-ttu-id="2fa44-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2fa44-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2fa44-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2fa44-106">\<behavior></span></span>  
<span data-ttu-id="2fa44-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="2fa44-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa44-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fa44-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fa44-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2fa44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2fa44-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fa44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fa44-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2fa44-111">Attributes</span></span>  
  
|<span data-ttu-id="2fa44-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2fa44-112">Attribute</span></span>|<span data-ttu-id="2fa44-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fa44-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2fa44-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="2fa44-114">allowUnsafeCaching</span></span>|<span data-ttu-id="2fa44-115">Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2fa44-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="2fa44-116">Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fa44-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="2fa44-117">Aber wenn Sie aktivieren möchten Zwischenspeichern legen Sie diese Eigenschaft auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="2fa44-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2fa44-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fa44-118">Child Elements</span></span>  
  
|<span data-ttu-id="2fa44-119">Element</span><span class="sxs-lookup"><span data-stu-id="2fa44-119">Element</span></span>|<span data-ttu-id="2fa44-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fa44-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fa44-121">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="2fa44-121">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="2fa44-122">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="2fa44-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="2fa44-123">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="2fa44-123">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="2fa44-124">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="2fa44-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fa44-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fa44-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2fa44-126">Element</span><span class="sxs-lookup"><span data-stu-id="2fa44-126">Element</span></span>|<span data-ttu-id="2fa44-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fa44-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fa44-128">\<Verhalten > der \<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2fa44-128">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2fa44-129">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2fa44-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fa44-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fa44-130">Remarks</span></span>  
 <span data-ttu-id="2fa44-131">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="2fa44-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="2fa44-132">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa44-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="2fa44-133">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa44-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="2fa44-134">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="2fa44-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="2fa44-135">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fa44-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="2fa44-136">Weitere Informationen zur Vorgehensweise beim Ändern des Freigabe von Ebenen und die cacheeinstellungen für die ChannelFactory und den channelcache Standardcache finden Sie unter [Ändern der Cachefreigabeebenen für Send-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="2fa44-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fa44-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fa44-137">Example</span></span>  
 <span data-ttu-id="2fa44-138">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="2fa44-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="2fa44-139">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="2fa44-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="2fa44-140">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit dem benutzerdefinierten factorycache und den channelcache factorycacheeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2fa44-140">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="2fa44-141">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="2fa44-141">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2fa44-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fa44-142">See also</span></span>
- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="2fa44-143">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="2fa44-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

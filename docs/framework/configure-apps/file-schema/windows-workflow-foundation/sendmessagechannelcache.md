---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: de53eb16d53d1e37209e36f2f6bfdc4bdfd84465
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947545"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="9fcb7-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="9fcb7-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="9fcb7-102">Ein Dienst Verhalten, das die Anpassung der Cache Freigabe Ebenen, der Einstellungen des channelfactorycaches und der Einstellungen des channelcaches für Workflows ermöglicht, die Nachrichten mithilfe von Sende Nachrichten Aktivitäten an Dienst Endpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="9fcb7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9fcb7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9fcb7-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9fcb7-104">\<behaviors></span></span>  
<span data-ttu-id="9fcb7-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9fcb7-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9fcb7-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9fcb7-106">\<behavior></span></span>  
<span data-ttu-id="9fcb7-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="9fcb7-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcb7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fcb7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fcb7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcb7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fcb7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fcb7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9fcb7-111">Attributes</span></span>  
  
|<span data-ttu-id="9fcb7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9fcb7-112">Attribute</span></span>|<span data-ttu-id="9fcb7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fcb7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fcb7-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="9fcb7-114">allowUnsafeCaching</span></span>|<span data-ttu-id="9fcb7-115">Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="9fcb7-116">Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="9fcb7-117">Wenn Sie die Zwischenspeicherung jedoch aktivieren möchten, legen Sie diese Eigenschaft auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fcb7-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcb7-118">Child Elements</span></span>  
  
|<span data-ttu-id="9fcb7-119">Element</span><span class="sxs-lookup"><span data-stu-id="9fcb7-119">Element</span></span>|<span data-ttu-id="9fcb7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fcb7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fcb7-121">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="9fcb7-121">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="9fcb7-122">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="9fcb7-123">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="9fcb7-123">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="9fcb7-124">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fcb7-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcb7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9fcb7-126">Element</span><span class="sxs-lookup"><span data-stu-id="9fcb7-126">Element</span></span>|<span data-ttu-id="9fcb7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fcb7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fcb7-128">\<Verhaltens > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="9fcb7-128">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9fcb7-129">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fcb7-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fcb7-130">Remarks</span></span>  
 <span data-ttu-id="9fcb7-131">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="9fcb7-132">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="9fcb7-133">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="9fcb7-134">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="9fcb7-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="9fcb7-135">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="9fcb7-136">Weitere Informationen zum Ändern der standardmäßigen Cache Freigabe Ebenen und Cache Einstellungen für die Kanalfactory und den channelcache finden Sie unter [Ändern der Cache Freigabe Ebenen für Sendeaktivitäten](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="9fcb7-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcb7-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fcb7-137">Example</span></span>  
 <span data-ttu-id="9fcb7-138">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="9fcb7-139">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="9fcb7-140">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die das `MyChannelCacheBehavior` Dienst Verhalten mit den Einstellungen für den benutzerdefinierten factorycache und den channelcache enthält.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-140">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="9fcb7-141">Dieses Dienst Verhalten wird dem Dienst über das `behaviorConfiguration` -Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9fcb7-141">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9fcb7-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fcb7-142">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="9fcb7-143">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="9fcb7-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

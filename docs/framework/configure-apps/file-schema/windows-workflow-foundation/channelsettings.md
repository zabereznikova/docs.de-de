---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: 9caf87bdf2029d273a9d6d7ac90b83ba72bafc7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945837"
---
# <a name="channelsettings"></a><span data-ttu-id="12f40-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="12f40-101">\<channelSettings></span></span>
<span data-ttu-id="12f40-102">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="12f40-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="12f40-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="12f40-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="12f40-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="12f40-104">\<behaviors></span></span>  
<span data-ttu-id="12f40-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="12f40-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="12f40-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="12f40-106">\<behavior></span></span>  
<span data-ttu-id="12f40-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="12f40-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="12f40-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="12f40-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f40-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="12f40-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12f40-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12f40-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12f40-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12f40-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12f40-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="12f40-112">Attributes</span></span>  
  
|<span data-ttu-id="12f40-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="12f40-113">Attribute</span></span>|<span data-ttu-id="12f40-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12f40-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12f40-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="12f40-115">idleTimeout</span></span>|<span data-ttu-id="12f40-116">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="12f40-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="12f40-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="12f40-117">leaseTimeout</span></span>|<span data-ttu-id="12f40-118">Ein TimeSpan-Wert, der das Zeitintervall angibt, nach dem ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="12f40-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="12f40-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="12f40-119">maxItemsInCache</span></span>|<span data-ttu-id="12f40-120">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="12f40-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12f40-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12f40-121">Child Elements</span></span>  
 <span data-ttu-id="12f40-122">Keine</span><span class="sxs-lookup"><span data-stu-id="12f40-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12f40-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12f40-123">Parent Elements</span></span>  
  
|<span data-ttu-id="12f40-124">Element</span><span class="sxs-lookup"><span data-stu-id="12f40-124">Element</span></span>|<span data-ttu-id="12f40-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12f40-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12f40-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="12f40-126">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="12f40-127">Ein Dienst Verhalten, das die Anpassung der Cache Freigabe Ebenen, der Einstellungen des channelfactorycaches und der Einstellungen des channelcaches für Workflows ermöglicht, die Nachrichten mithilfe von Sende Nachrichten Aktivitäten an Dienst Endpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="12f40-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12f40-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12f40-128">Remarks</span></span>  
 <span data-ttu-id="12f40-129">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="12f40-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="12f40-130">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="12f40-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="12f40-131">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="12f40-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="12f40-132">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="12f40-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="12f40-133">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="12f40-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="12f40-134">Weitere Informationen zum Ändern der standardmäßigen Cache Freigabe Ebenen und Cache Einstellungen für die Kanalfactory und den channelcache finden Sie unter [Ändern der Cache Freigabe Ebenen für Sendeaktivitäten](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="12f40-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12f40-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12f40-135">Example</span></span>  
 <span data-ttu-id="12f40-136">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="12f40-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="12f40-137">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="12f40-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="12f40-138">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die das `MyChannelCacheBehavior` Dienst Verhalten mit den Einstellungen für den benutzerdefinierten factorycache und den channelcache enthält.</span><span class="sxs-lookup"><span data-stu-id="12f40-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="12f40-139">Dieses Dienst Verhalten wird dem Dienst über das `behaviorConfiguration` -Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12f40-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12f40-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12f40-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="12f40-141">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="12f40-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

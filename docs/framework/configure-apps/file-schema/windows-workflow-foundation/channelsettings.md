---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f70e30c903fa9bfc3f5d6054ef2ec34bf1b3cba1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790207"
---
# <a name="channelsettings"></a><span data-ttu-id="59c37-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="59c37-101">\<channelSettings></span></span>
<span data-ttu-id="59c37-102">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="59c37-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="59c37-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59c37-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="59c37-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="59c37-104">\<behaviors></span></span>  
<span data-ttu-id="59c37-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="59c37-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="59c37-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="59c37-106">\<behavior></span></span>  
<span data-ttu-id="59c37-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="59c37-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="59c37-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="59c37-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c37-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="59c37-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59c37-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59c37-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59c37-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59c37-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59c37-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="59c37-112">Attributes</span></span>  
  
|<span data-ttu-id="59c37-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="59c37-113">Attribute</span></span>|<span data-ttu-id="59c37-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59c37-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59c37-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="59c37-115">idleTimeout</span></span>|<span data-ttu-id="59c37-116">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="59c37-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="59c37-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="59c37-117">leaseTimeout</span></span>|<span data-ttu-id="59c37-118">Ein TimeSpan-Wert, der das Zeitintervall angibt, nach der ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="59c37-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="59c37-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="59c37-119">maxItemsInCache</span></span>|<span data-ttu-id="59c37-120">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="59c37-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59c37-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59c37-121">Child Elements</span></span>  
 <span data-ttu-id="59c37-122">Keine</span><span class="sxs-lookup"><span data-stu-id="59c37-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59c37-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59c37-123">Parent Elements</span></span>  
  
|<span data-ttu-id="59c37-124">Element</span><span class="sxs-lookup"><span data-stu-id="59c37-124">Element</span></span>|<span data-ttu-id="59c37-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59c37-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59c37-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="59c37-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="59c37-127">Ein Dienstverhalten, das es, die cachefreigabeebenen Ebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden ermöglicht-messagingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="59c37-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59c37-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59c37-128">Remarks</span></span>  
 <span data-ttu-id="59c37-129">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="59c37-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="59c37-130">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="59c37-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="59c37-131">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="59c37-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="59c37-132">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="59c37-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="59c37-133">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59c37-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="59c37-134">Weitere Informationen zur Vorgehensweise beim Ändern des Freigabe von Ebenen und die cacheeinstellungen für die ChannelFactory und den channelcache Standardcache finden Sie unter [Ändern der Cachefreigabeebenen für Send-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="59c37-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59c37-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59c37-135">Example</span></span>  
 <span data-ttu-id="59c37-136">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="59c37-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="59c37-137">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="59c37-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="59c37-138">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit dem benutzerdefinierten factorycache und den channelcache factorycacheeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="59c37-138">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="59c37-139">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="59c37-139">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59c37-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59c37-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="59c37-141">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="59c37-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

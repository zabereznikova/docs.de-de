---
title: '&lt;factorySettings&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: bb57378ab692d3ddb0728a7f6c4e5bf039e59d15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637845"
---
# <a name="ltfactorysettingsgt"></a><span data-ttu-id="28896-102">&lt;factorySettings&gt;</span><span class="sxs-lookup"><span data-stu-id="28896-102">&lt;factorySettings&gt;</span></span>
<span data-ttu-id="28896-103">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="28896-103">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="28896-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="28896-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="28896-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="28896-105">\<behaviors></span></span>  
<span data-ttu-id="28896-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="28896-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="28896-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="28896-107">\<behavior></span></span>  
<span data-ttu-id="28896-108">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="28896-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="28896-109">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="28896-109">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28896-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="28896-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28896-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28896-111">Attributes and Elements</span></span>  
 <span data-ttu-id="28896-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28896-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28896-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="28896-113">Attributes</span></span>  
  
|<span data-ttu-id="28896-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="28896-114">Attribute</span></span>|<span data-ttu-id="28896-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28896-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28896-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="28896-116">idleTimeout</span></span>|<span data-ttu-id="28896-117">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="28896-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="28896-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="28896-118">leaseTimeout</span></span>|<span data-ttu-id="28896-119">Ein TimeSpan-Wert, der das Zeitintervall angibt, nach der ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="28896-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="28896-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="28896-120">maxItemsInCache</span></span>|<span data-ttu-id="28896-121">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="28896-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28896-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28896-122">Child Elements</span></span>  
 <span data-ttu-id="28896-123">Keine</span><span class="sxs-lookup"><span data-stu-id="28896-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28896-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28896-124">Parent Elements</span></span>  
  
|<span data-ttu-id="28896-125">Element</span><span class="sxs-lookup"><span data-stu-id="28896-125">Element</span></span>|<span data-ttu-id="28896-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28896-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28896-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="28896-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="28896-128">Ein Dienstverhalten, das es, die cachefreigabeebenen Ebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden ermöglicht-messagingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="28896-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28896-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28896-129">Remarks</span></span>  
 <span data-ttu-id="28896-130">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="28896-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="28896-131">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="28896-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="28896-132">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="28896-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="28896-133">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="28896-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="28896-134">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="28896-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="28896-135">Weitere Informationen zur Vorgehensweise beim Ändern des Freigabe von Ebenen und die cacheeinstellungen für die ChannelFactory und den channelcache Standardcache finden Sie unter [Ändern der Cachefreigabeebenen für Send-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="28896-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28896-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28896-136">Example</span></span>  
 <span data-ttu-id="28896-137">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="28896-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="28896-138">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="28896-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="28896-139">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit dem benutzerdefinierten factorycache und den channelcache factorycacheeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="28896-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="28896-140">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="28896-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28896-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28896-141">See also</span></span>
- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="28896-142">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="28896-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

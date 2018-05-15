---
title: '&lt;factorySettings&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: 36f0b82afa8aa8738d2927dc52e1b00e07e72bb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfactorysettingsgt"></a><span data-ttu-id="64a4c-102">&lt;factorySettings&gt;</span><span class="sxs-lookup"><span data-stu-id="64a4c-102">&lt;factorySettings&gt;</span></span>
<span data-ttu-id="64a4c-103">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="64a4c-103">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="64a4c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="64a4c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="64a4c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="64a4c-105">\<behaviors></span></span>  
<span data-ttu-id="64a4c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="64a4c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="64a4c-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="64a4c-107">\<behavior></span></span>  
<span data-ttu-id="64a4c-108">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="64a4c-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="64a4c-109">\<FactorySettings ></span><span class="sxs-lookup"><span data-stu-id="64a4c-109">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a4c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="64a4c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64a4c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="64a4c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="64a4c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64a4c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64a4c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="64a4c-113">Attributes</span></span>  
  
|<span data-ttu-id="64a4c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="64a4c-114">Attribute</span></span>|<span data-ttu-id="64a4c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64a4c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64a4c-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="64a4c-116">idleTimeout</span></span>|<span data-ttu-id="64a4c-117">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64a4c-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="64a4c-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="64a4c-118">leaseTimeout</span></span>|<span data-ttu-id="64a4c-119">Ein TimeSpan-Wert, der das Zeitintervall angibt, nach denen ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="64a4c-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="64a4c-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="64a4c-120">maxItemsInCache</span></span>|<span data-ttu-id="64a4c-121">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="64a4c-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64a4c-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64a4c-122">Child Elements</span></span>  
 <span data-ttu-id="64a4c-123">Keine</span><span class="sxs-lookup"><span data-stu-id="64a4c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64a4c-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64a4c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="64a4c-125">Element</span><span class="sxs-lookup"><span data-stu-id="64a4c-125">Element</span></span>|<span data-ttu-id="64a4c-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64a4c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64a4c-127">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="64a4c-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="64a4c-128">Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64a4c-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64a4c-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64a4c-129">Remarks</span></span>  
 <span data-ttu-id="64a4c-130">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="64a4c-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="64a4c-131">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="64a4c-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="64a4c-132">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="64a4c-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="64a4c-133">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="64a4c-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="64a4c-134">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="64a4c-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="64a4c-135">Weitere Informationen zum Ändern des cachefreigabeebenen und cacheeinstellungen für die Kanalfactory und den kanalcache Standardcaches finden Sie unter [ändern die Cachefreigabeebenen für Aktivitäten senden](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="64a4c-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64a4c-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64a4c-136">Example</span></span>  
 <span data-ttu-id="64a4c-137">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="64a4c-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="64a4c-138">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="64a4c-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="64a4c-139">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit cacheeinstellungen für die benutzerdefinierte Factory und den channelcache.</span><span class="sxs-lookup"><span data-stu-id="64a4c-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="64a4c-140">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.</span><span class="sxs-lookup"><span data-stu-id="64a4c-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64a4c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64a4c-141">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [<span data-ttu-id="64a4c-142">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="64a4c-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: b68c6d2e526eb22328806558d7c167b7f2ed0820
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152000"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="2bfb0-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="2bfb0-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="2bfb0-102">Ein Dienstverhalten, das es ermöglicht, die Cachefreigabeebenen anzupassen sowie die Einstellungen des Channelfactorycaches und des Channelcaches für Workflows festzulegen, die Meldungen mit Senden-Messagingaktivitäten an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="2bfb0-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2bfb0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2bfb0-104">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2bfb0-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2bfb0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2bfb0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2bfb0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2bfb0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2bfb0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2bfb0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2bfb0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span><span class="sxs-lookup"><span data-stu-id="2bfb0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfb0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bfb0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bfb0-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2bfb0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2bfb0-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bfb0-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="2bfb0-112">Attributes</span></span>  
  
|<span data-ttu-id="2bfb0-113">attribute</span><span class="sxs-lookup"><span data-stu-id="2bfb0-113">Attribute</span></span>|<span data-ttu-id="2bfb0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bfb0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2bfb0-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="2bfb0-115">allowUnsafeCaching</span></span>|<span data-ttu-id="2bfb0-116">Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="2bfb0-117">Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="2bfb0-118">Wenn Sie jedoch die Zwischenspeicherung aktivieren möchten, legen Sie diese Eigenschaft auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bfb0-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2bfb0-119">Child Elements</span></span>  
  
|<span data-ttu-id="2bfb0-120">Element</span><span class="sxs-lookup"><span data-stu-id="2bfb0-120">Element</span></span>|<span data-ttu-id="2bfb0-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bfb0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bfb0-122">\<channelEinstellungen></span><span class="sxs-lookup"><span data-stu-id="2bfb0-122">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="2bfb0-123">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="2bfb0-124">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="2bfb0-124">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="2bfb0-125">Gibt die Einstellungen des Channelfactorycaches an.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bfb0-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2bfb0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2bfb0-127">Element</span><span class="sxs-lookup"><span data-stu-id="2bfb0-127">Element</span></span>|<span data-ttu-id="2bfb0-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bfb0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bfb0-129">\<Verhalten> \<von serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2bfb0-129">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2bfb0-130">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bfb0-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2bfb0-131">Remarks</span></span>  
 <span data-ttu-id="2bfb0-132">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="2bfb0-133">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="2bfb0-134">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="2bfb0-135">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="2bfb0-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="2bfb0-136">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="2bfb0-137">Weitere Informationen zum Ändern der Standardcachefreigabeebenen und Cacheeinstellungen für die Kanalfactory und den Kanalcache finden Sie unter [Ändern der Cachefreigabeebenen für Sendeaktivitäten](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="2bfb0-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfb0-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bfb0-138">Example</span></span>  
 <span data-ttu-id="2bfb0-139">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="2bfb0-140">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="2bfb0-141">Das folgende Beispiel zeigt den Inhalt einer `MyChannelCacheBehavior` Konfigurationsdatei, die das Dienstverhalten mit den benutzerdefinierten Factorycache- und Kanalcacheeinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-141">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="2bfb0-142">Dieses Dienstverhalten wird dem Dienst `behaviorConfiguration` über das Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-142">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2bfb0-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bfb0-143">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="2bfb0-144">Ändern der Cachefreigabeebenen für Sendeaktivitäten</span><span class="sxs-lookup"><span data-stu-id="2bfb0-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: ef806669470595638de124a480513db13674af51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202408"
---
# \<channelSettings>

<span data-ttu-id="ab243-101">Gibt die Einstellungen des Channelcaches an.</span><span class="sxs-lookup"><span data-stu-id="ab243-101">Specifies the settings of the channel cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="ab243-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab243-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab243-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab243-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ab243-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab243-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab243-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab243-105">Attributes</span></span>  
  
|<span data-ttu-id="ab243-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ab243-106">Attribute</span></span>|<span data-ttu-id="ab243-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab243-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab243-108">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="ab243-108">idleTimeout</span></span>|<span data-ttu-id="ab243-109">Ein TimeSpan-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab243-109">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="ab243-110">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="ab243-110">leaseTimeout</span></span>|<span data-ttu-id="ab243-111">Ein TimeSpan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein Objekt aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ab243-111">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="ab243-112">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="ab243-112">maxItemsInCache</span></span>|<span data-ttu-id="ab243-113">Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="ab243-113">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab243-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab243-114">Child Elements</span></span>  

 <span data-ttu-id="ab243-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ab243-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab243-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab243-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ab243-117">Element</span><span class="sxs-lookup"><span data-stu-id="ab243-117">Element</span></span>|<span data-ttu-id="ab243-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab243-118">Description</span></span>|  
|-------------|-----------------|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="ab243-119">Ein Dienstverhalten, das es ermöglicht, die Cachefreigabeebenen anzupassen sowie die Einstellungen des Channelfactorycaches und des Channelcaches für Workflows festzulegen, die Meldungen mit Senden-Messagingaktivitäten an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="ab243-119">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab243-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ab243-120">Remarks</span></span>  

 <span data-ttu-id="ab243-121">Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="ab243-121">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="ab243-122">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ab243-122">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="ab243-123">Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab243-123">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="ab243-124">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="ab243-124">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="ab243-125">In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ab243-125">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="ab243-126">Weitere Informationen zum Ändern der standardmäßigen Cache Freigabe Ebenen und Cache Einstellungen für die Kanalfactory und den channelcache finden Sie unter [Ändern der Cache Freigabe Ebenen für Sendeaktivitäten](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="ab243-126">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab243-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab243-127">Example</span></span>  

 <span data-ttu-id="ab243-128">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ab243-128">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="ab243-129">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab243-129">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="ab243-130">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die das `MyChannelCacheBehavior`  Dienst Verhalten mit den Einstellungen für den benutzerdefinierten factorycache und den channelcache enthält.</span><span class="sxs-lookup"><span data-stu-id="ab243-130">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="ab243-131">Dieses Dienst Verhalten wird dem Dienst über das-Attribut hinzugefügt `behaviorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ab243-131">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab243-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab243-132">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="ab243-133">Ändern der Cachefreigabeebenen für Send-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="ab243-133">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

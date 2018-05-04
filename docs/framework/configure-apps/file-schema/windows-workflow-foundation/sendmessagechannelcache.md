---
title: '&lt;sendmessagechannelcache an&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 9fb68fb8ef4b1fa74a36005c80dc568e227c6473
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsendmessagechannelcachegt"></a>&lt;sendmessagechannelcache an&gt;
Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<sendmessagechannelcache an >  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|allowUnsafeCaching|Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist. Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert. Jedoch, wenn Sie aktivieren möchten Zwischenspeichern auf legen Sie diese Eigenschaft auf **"true"**.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ChannelSettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|Gibt die Einstellungen des Channelcaches an.|  
|[\<FactorySettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|Gibt die Einstellungen des Channelfactorycaches an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten > der \<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden. Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.  
  
 Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> (Zwischenspeichern auf Hostebene) gemeinsam verwendet. Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene). In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.  
  
 Weitere Informationen zum Ändern des cachefreigabeebenen und cacheeinstellungen für die Kanalfactory und den kanalcache Standardcaches finden Sie unter [ändern die Cachefreigabeebenen für Aktivitäten senden](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
## <a name="example"></a>Beispiel  
 In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben. Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu. Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die **MyChannelCacheBehavior** -Dienstverhalten mit cacheeinstellungen für die benutzerdefinierte Factory und den channelcache. Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die **BehaviorConfiguarion** Attribut.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [Ändern der Cachefreigabeebenen für Sendeaktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

---
title: "&lt;sendMessageChannelCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;sendMessageChannelCache&gt;
Ein Dienstverhalten, das es ermöglicht, die Cachefreigabeebenen anzupassen sowie die Einstellungen des Channelfactorycaches und des Channelcaches für Workflows festzulegen, die Meldungen mit Senden\-Messagingaktivitäten an Dienstendpunkte senden.  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
       <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
           <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
           <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
       </sendMessageChannelCache>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|allowUnsafeCaching|Ein boolescher Wert, der angibt, ob das Zwischenspeichern aktiviert ist.  Wenn der Workflowdienst benutzerdefinierte Bindungen oder benutzerdefiniertes Verhalten aufweist, könnte das Zwischenspeichern unsicher sein und ist daher standardmäßig deaktiviert.  Wenn Sie jedoch das Zwischenspeichern aktivieren möchten, dann legen Sie diese Eigenschaft auf **true** fest.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<channelSettings\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|Gibt die Einstellungen des Channelcaches an.|  
|[\<factorySettings\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|Gibt die Einstellungen des Channelfactorycaches an.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<behavior\> von \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## Hinweise  
 Dieses Dienstverhalten ist für Workflows bestimmt, die Meldungen an Dienstendpunkte senden.  Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.  
  
 Standardmäßig wird in einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow der von <xref:System.ServiceModel.Activities.Send>\-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen im <xref:System.ServiceModel.WorkflowServiceHost> \(Zwischenspeichern auf Hostebene\) gemeinsam verwendet.  Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung \(Zwischenspeichern auf Instanzebene\).  In einem Workflow, der in der Konfiguration definierte Endpunkte besitzt, ist das Zwischenspeichern für jede Sendeaktivität standardmäßig deaktiviert.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] dazu, wie die Standardcachefreigabeebenen und die Cacheeinstellungen für die Channelfactory und den Channelcache geändert werden, finden Sie unter [Ändern der Cachefreigabeebenen für Send\-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
## Beispiel  
 In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.  Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.  Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die das **MyChannelCacheBehavior** \-Dienstverhalten mit dem benutzerdefinierten Factorycache und den Channelcacheeinstellungen enthält.  Dieses Dienstverhalten wird dem Dienst mithilfe des **behaviorConfiguarion** \-Attributs hinzugefügt.  
  
```  
  
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
  
## Siehe auch  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>   
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>   
 <xref:System.ServiceModel.Activities.Send>   
 [Ändern der Cachefreigabeebenen für Send\-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
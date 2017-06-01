---
title: "&lt;channelSettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;channelSettings&gt;
Gibt die Einstellungen des Channelcaches an.  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
       <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
           <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
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
|idleTimeout|Ein TimeSpan\-Wert, der die maximale Zeitspanne angibt, während der das Objekt im Cache im Leerlauf verbleiben kann, bevor es freigegeben wird.|  
|leaseTimeout|Ein TimeSpan\-Wert, der den Zeitraum angibt, nach dessen Ablauf ein Objekt aus dem Cache entfernt wird.|  
|maxItemsInCache|Eine ganze Zahl, die die maximale Anzahl an Objekten angibt, die im Cache gespeichert werden können.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Ein Dienstverhalten, das es ermöglicht, die Cachefreigabeebenen anzupassen sowie die Einstellungen des Channelfactorycaches und des Channelcaches für Workflows festzulegen, die Meldungen mit Senden\-Messagingaktivitäten an Dienstendpunkte senden.|  
  
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
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>   
 [Ändern der Cachefreigabeebenen für Send\-Aktivitäten](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
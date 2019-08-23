---
title: <behavior>des <serviceBehaviors> Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946076"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a>\<Verhaltens > von \<Service Verhaltens> des Workflows
Das **Behavior** -Element enthält eine Sammlung von Einstellungen für das Verhalten eines Dienstanbieter. Jedes Verhalten wird anhand seines **namens**indiziert. Dienste können mit dem Behavior- **Configuration** -Attribut des [ \<Endpoint >](../wcf/endpoint-element.md) -Elements über diesen Namen mit den einzelnen Verhalten verknüpft werden. Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  hostLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|Ein Dienst Verhalten, das einem Dienst ermöglicht, die ETW-nach <xref:System.Activities.Tracking.EtwTrackingParticipant>Verfolgung mit einem zu verwenden.|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|Ein Dienst Verhalten, das die Anpassung der Cache Freigabe Ebenen, der Einstellungen des channelfactorycaches und der Einstellungen des channelcaches für Workflows ermöglicht, die Nachrichten mithilfe von Sende Nachrichten Aktivitäten an Dienst Endpunkte senden.|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|Ein Dienst Verhalten, mit dem Sie die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Funktion konfigurieren können, die das Beibehalten von Zustandsinformationen für Workflow Dienst Instanzen in eine SQL Server 2005-oder SQL Server 2008-Datenbank unterstützt.|  
|[\<workflowIdle>](workflowidle.md)|Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceverhaltens>](servicebehaviors-of-workflow.md)|Eine Auflistung von Dienstverhaltenselementen.|

---
title: '&lt;behavior&gt; von &lt;serviceBehaviors&gt; des Workflows'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 303cf3a8f954b20beaa76fb46294dbb37488fd61
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a>&lt;behavior&gt; von &lt;serviceBehaviors&gt; des Workflows
Die **Verhalten** Element enthält eine Auflistung von Einstellungen für das Verhalten eines Diensts. Jedes Verhalten wird durch indiziert die **Namen**. Dienste können eine Verknüpfung zu jedem Verhalten über diesen Namen mit der **BehaviorConfiguration**Attribut von der [ \<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element. Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
  
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
                                  honstLockRenewalPeriod="TimeSpan" 
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
|[\<BufferReceive >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.|  
|[\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Ein Dienstverhalten, das einen Dienst für die Nutzung von ETW-nachverfolgung mit ermöglicht eine <xref:System.Activities.Tracking.EtwTrackingParticipant>.|  
|[\<sendmessagechannelcache an >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.|  
|[\<SqlWorkflowInstanceStore >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|Ein Dienstverhalten, die Sie konfigurieren kann die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> -Funktion, die Speichern von Zustandsinformationen für workflowdienstinstanzen in eine SQL Server 2005 oder SQL Server 2008-Datenbank unterstützt.|  
|[\<WorkflowIdle >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.|  
|[\<WorkflowInstanceManagement >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.|  
|[\<WorkflowUnhandledException >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Eine Auflistung von Dienstverhaltenselementen.|

---
title: '&lt;behavior&gt; von &lt;serviceBehaviors&gt; des Workflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ce452b97b31f1d552eda481d2f514857372e2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="9cf52-102">&lt;behavior&gt; von &lt;serviceBehaviors&gt; des Workflows</span><span class="sxs-lookup"><span data-stu-id="9cf52-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="9cf52-103">Die **Verhalten** Element enthält eine Auflistung von Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="9cf52-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="9cf52-104">Jedes Verhalten wird durch indiziert die **Namen**.</span><span class="sxs-lookup"><span data-stu-id="9cf52-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="9cf52-105">Dienste können eine Verknüpfung zu jedem Verhalten über diesen Namen mit der **BehaviorConfiguration**Attribut von der [ \<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9cf52-105">Services can link to each behavior through this name using the **behaviorConfiguration**attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="9cf52-106">Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9cf52-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="9cf52-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9cf52-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="9cf52-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9cf52-108">\<behaviors></span></span>  
<span data-ttu-id="9cf52-109">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9cf52-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="9cf52-110">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9cf52-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf52-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf52-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf52-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf52-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9cf52-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9cf52-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf52-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="9cf52-114">Attributes</span></span>  
  
|<span data-ttu-id="9cf52-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="9cf52-115">Attribute</span></span>|<span data-ttu-id="9cf52-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cf52-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cf52-117">Name</span><span class="sxs-lookup"><span data-stu-id="9cf52-117">name</span></span>|<span data-ttu-id="9cf52-118">Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.</span><span class="sxs-lookup"><span data-stu-id="9cf52-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9cf52-119">Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.</span><span class="sxs-lookup"><span data-stu-id="9cf52-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cf52-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf52-120">Child Elements</span></span>  
  
|<span data-ttu-id="9cf52-121">Element</span><span class="sxs-lookup"><span data-stu-id="9cf52-121">Element</span></span>|<span data-ttu-id="9cf52-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cf52-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf52-123">\<BufferReceive ></span><span class="sxs-lookup"><span data-stu-id="9cf52-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="9cf52-124">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="9cf52-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="9cf52-125">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="9cf52-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="9cf52-126">Ein Dienstverhalten, das einen Dienst für die Nutzung von ETW-nachverfolgung mit ermöglicht eine <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="9cf52-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="9cf52-127">\<sendmessagechannelcache an ></span><span class="sxs-lookup"><span data-stu-id="9cf52-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="9cf52-128">Ein Dienstverhalten, die es ermöglicht die Anpassung der cachefreigabeebenen, die Einstellungen des channelfactorycaches und die Einstellungen des channelcaches für Workflows, die für das Senden von Nachrichten an Dienstendpunkte senden Messagingaktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cf52-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="9cf52-129">\<SqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="9cf52-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="9cf52-130">Ein Dienstverhalten, die Sie konfigurieren kann die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> -Funktion, die Speichern von Zustandsinformationen für workflowdienstinstanzen in eine SQL Server 2005 oder SQL Server 2008-Datenbank unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9cf52-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="9cf52-131">\<WorkflowIdle ></span><span class="sxs-lookup"><span data-stu-id="9cf52-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="9cf52-132">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="9cf52-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="9cf52-133">\<WorkflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="9cf52-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="9cf52-134">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="9cf52-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="9cf52-135">\<WorkflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="9cf52-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="9cf52-136">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="9cf52-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf52-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf52-137">Parent Elements</span></span>  
  
|<span data-ttu-id="9cf52-138">Element</span><span class="sxs-lookup"><span data-stu-id="9cf52-138">Element</span></span>|<span data-ttu-id="9cf52-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cf52-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf52-140">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9cf52-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="9cf52-141">Eine Auflistung von Dienstverhaltenselementen.</span><span class="sxs-lookup"><span data-stu-id="9cf52-141">A collection of service behavior elements.</span></span>|

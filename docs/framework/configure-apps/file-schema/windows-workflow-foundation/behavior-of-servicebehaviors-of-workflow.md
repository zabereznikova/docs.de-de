---
title: <behavior>von <serviceBehaviors> Workflow
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152319"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="5d178-102">\<Verhalten> \<von serviceVerhalten> workflow</span><span class="sxs-lookup"><span data-stu-id="5d178-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="5d178-103">Das **Verhaltenselement** enthält eine Auflistung von Einstellungen für das Verhalten eines Dienstes.</span><span class="sxs-lookup"><span data-stu-id="5d178-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="5d178-104">Jedes Verhalten wird anhand seines **Namens**indiziert.</span><span class="sxs-lookup"><span data-stu-id="5d178-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="5d178-105">Dienste können über diesen Namen mit dem **behaviorConfiguration-Attribut** des [ \<Endpunkts>-Element](../wcf/endpoint-element.md) mit jedem Verhalten verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="5d178-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="5d178-106">Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5d178-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="5d178-107">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d178-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d178-108">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d178-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5d178-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Verhalten>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d178-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="5d178-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d178-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="5d178-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Verhalten>**</span><span class="sxs-lookup"><span data-stu-id="5d178-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d178-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d178-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d178-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d178-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5d178-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d178-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d178-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="5d178-115">Attributes</span></span>  
  
|<span data-ttu-id="5d178-116">attribute</span><span class="sxs-lookup"><span data-stu-id="5d178-116">Attribute</span></span>|<span data-ttu-id="5d178-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d178-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d178-118">name</span><span class="sxs-lookup"><span data-stu-id="5d178-118">name</span></span>|<span data-ttu-id="5d178-119">Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.</span><span class="sxs-lookup"><span data-stu-id="5d178-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="5d178-120">Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.</span><span class="sxs-lookup"><span data-stu-id="5d178-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d178-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d178-121">Child Elements</span></span>  
  
|<span data-ttu-id="5d178-122">Element</span><span class="sxs-lookup"><span data-stu-id="5d178-122">Element</span></span>|<span data-ttu-id="5d178-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d178-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d178-124">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="5d178-124">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="5d178-125">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="5d178-125">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="5d178-126">\<Routing-></span><span class="sxs-lookup"><span data-stu-id="5d178-126">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="5d178-127">Ein Dienstverhalten, das einem Dienst ermöglicht, die ETW-Nachverfolgung mit einem <xref:System.Activities.Tracking.EtwTrackingParticipant> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d178-127">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="5d178-128">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="5d178-128">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="5d178-129">Ein Dienstverhalten, das es ermöglicht, die Cachefreigabeebenen anzupassen sowie die Einstellungen des Channelfactorycaches und des Channelcaches für Workflows festzulegen, die Meldungen mit Senden-Messagingaktivitäten an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="5d178-129">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="5d178-130">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="5d178-130">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="5d178-131">Ein Dienstverhalten, das es ermöglicht, die Funktion <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> zu konfigurieren, die das Beibehalten von Zustandsinformationen für Workflowdienstinstanzen in eine SQL Server 2005- oder SQL Server 2008-Datenbank unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d178-131">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="5d178-132">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="5d178-132">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="5d178-133">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="5d178-133">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="5d178-134">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="5d178-134">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="5d178-135">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="5d178-135">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="5d178-136">\<WorkflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="5d178-136">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="5d178-137">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="5d178-137">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d178-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d178-138">Parent Elements</span></span>  
  
|<span data-ttu-id="5d178-139">Element</span><span class="sxs-lookup"><span data-stu-id="5d178-139">Element</span></span>|<span data-ttu-id="5d178-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d178-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d178-141">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5d178-141">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="5d178-142">Eine Auflistung von Dienstverhaltenselementen.</span><span class="sxs-lookup"><span data-stu-id="5d178-142">A collection of service behavior elements.</span></span>|

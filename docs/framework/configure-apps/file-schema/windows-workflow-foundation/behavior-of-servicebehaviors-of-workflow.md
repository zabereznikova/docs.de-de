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
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="3ab5c-102">\<Verhaltens > von \<Service Verhaltens> des Workflows</span><span class="sxs-lookup"><span data-stu-id="3ab5c-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="3ab5c-103">Das **Behavior** -Element enthält eine Sammlung von Einstellungen für das Verhalten eines Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="3ab5c-104">Jedes Verhalten wird anhand seines **namens**indiziert.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="3ab5c-105">Dienste können mit dem Behavior- **Configuration** -Attribut des [ \<Endpoint >](../wcf/endpoint-element.md) -Elements über diesen Namen mit den einzelnen Verhalten verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="3ab5c-106">Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="3ab5c-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3ab5c-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="3ab5c-108">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3ab5c-108">\<behaviors></span></span>  
<span data-ttu-id="3ab5c-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3ab5c-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="3ab5c-110">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3ab5c-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab5c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ab5c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ab5c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3ab5c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3ab5c-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ab5c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3ab5c-114">Attributes</span></span>  
  
|<span data-ttu-id="3ab5c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="3ab5c-115">Attribute</span></span>|<span data-ttu-id="3ab5c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ab5c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ab5c-117">Name</span><span class="sxs-lookup"><span data-stu-id="3ab5c-117">name</span></span>|<span data-ttu-id="3ab5c-118">Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="3ab5c-119">Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ab5c-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ab5c-120">Child Elements</span></span>  
  
|<span data-ttu-id="3ab5c-121">Element</span><span class="sxs-lookup"><span data-stu-id="3ab5c-121">Element</span></span>|<span data-ttu-id="3ab5c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ab5c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ab5c-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="3ab5c-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="3ab5c-124">Ein Dienstverhalten, das es dem Dienst ermöglicht, gepufferte Empfangsverarbeitung zu verwenden. Dadurch kann ein Workflowdienst Nachrichten verarbeiten, die nicht in der richtigen Reihenfolge vorliegen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="3ab5c-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="3ab5c-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="3ab5c-126">Ein Dienst Verhalten, das einem Dienst ermöglicht, die ETW-nach <xref:System.Activities.Tracking.EtwTrackingParticipant>Verfolgung mit einem zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="3ab5c-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="3ab5c-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="3ab5c-128">Ein Dienst Verhalten, das die Anpassung der Cache Freigabe Ebenen, der Einstellungen des channelfactorycaches und der Einstellungen des channelcaches für Workflows ermöglicht, die Nachrichten mithilfe von Sende Nachrichten Aktivitäten an Dienst Endpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="3ab5c-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="3ab5c-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="3ab5c-130">Ein Dienst Verhalten, mit dem Sie die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Funktion konfigurieren können, die das Beibehalten von Zustandsinformationen für Workflow Dienst Instanzen in eine SQL Server 2005-oder SQL Server 2008-Datenbank unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="3ab5c-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="3ab5c-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="3ab5c-132">Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="3ab5c-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="3ab5c-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="3ab5c-134">Ein Dienstverhalten, das es ermöglicht, Einstellungen anzugeben, die steuern, wie Workflowinstanzen ausgeführt werden. Diese Einstellungen bestimmen auch die Dauerhaftigkeit sowie das Verhalten bei nicht behandelten Ausnahmen und im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="3ab5c-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="3ab5c-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="3ab5c-136">Ein Dienstverhalten, das es ermöglicht, die Aktion anzugeben, die durchgeführt werden soll, wenn eine nicht behandelte Ausnahme innerhalb eines Workflowdiensts auftritt.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ab5c-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ab5c-137">Parent Elements</span></span>  
  
|<span data-ttu-id="3ab5c-138">Element</span><span class="sxs-lookup"><span data-stu-id="3ab5c-138">Element</span></span>|<span data-ttu-id="3ab5c-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ab5c-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ab5c-140">\<serviceverhaltens></span><span class="sxs-lookup"><span data-stu-id="3ab5c-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="3ab5c-141">Eine Auflistung von Dienstverhaltenselementen.</span><span class="sxs-lookup"><span data-stu-id="3ab5c-141">A collection of service behavior elements.</span></span>|

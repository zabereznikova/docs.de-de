---
title: '&lt;system.serviceModel&gt; des Workflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97247abe629d12b6c60d8157786b9b82e9e14f4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="d1e8d-102">&lt;system.serviceModel&gt; des Workflows</span><span class="sxs-lookup"><span data-stu-id="d1e8d-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="d1e8d-103">Dieser Konfigurationsabschnitt enthält alle Workflowkonfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1e8d-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName="String"   
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>    
     <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
     </participants>   
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1e8d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d1e8d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d1e8d-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1e8d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d1e8d-107">Attributes</span></span>  
 <span data-ttu-id="d1e8d-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d1e8d-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1e8d-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1e8d-109">Child Elements</span></span>  
  
|<span data-ttu-id="d1e8d-110">Element</span><span class="sxs-lookup"><span data-stu-id="d1e8d-110">Element</span></span>|<span data-ttu-id="d1e8d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1e8d-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1e8d-112">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d1e8d-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="d1e8d-113">Dieser Abschnitt definiert die **ServiceBehaviors** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="d1e8d-114">Jedes Element der Auflistung definiert von Diensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="d1e8d-115">Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="d1e8d-116">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="d1e8d-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="d1e8d-117">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="d1e8d-118">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren der nachverfolgung für einen Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d1e8d-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1e8d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1e8d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d1e8d-120">Element</span><span class="sxs-lookup"><span data-stu-id="d1e8d-120">Element</span></span>|<span data-ttu-id="d1e8d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1e8d-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1e8d-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d1e8d-122">\<configuration></span></span>|<span data-ttu-id="d1e8d-123">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-123">The root element for all configuration elements in a .NET configuration file.</span></span>|

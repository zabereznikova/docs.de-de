---
title: <system.serviceModel> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 005a274df9e9ab99227a3748b7a25c9d465d020f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271127"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="87fc2-102">\<system.serviceModel > des Workflows</span><span class="sxs-lookup"><span data-stu-id="87fc2-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="87fc2-103">Dieser Konfigurationsabschnitt enthält alle Workflowkonfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="87fc2-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87fc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87fc2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87fc2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87fc2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="87fc2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87fc2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87fc2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="87fc2-107">Attributes</span></span>  
 <span data-ttu-id="87fc2-108">Keine</span><span class="sxs-lookup"><span data-stu-id="87fc2-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87fc2-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87fc2-109">Child Elements</span></span>  
  
|<span data-ttu-id="87fc2-110">Element</span><span class="sxs-lookup"><span data-stu-id="87fc2-110">Element</span></span>|<span data-ttu-id="87fc2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87fc2-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87fc2-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="87fc2-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="87fc2-113">Dieser Abschnitt definiert die **ServiceBehaviors** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="87fc2-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="87fc2-114">Jedes Element der Auflistung definiert von Diensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="87fc2-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="87fc2-115">Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.</span><span class="sxs-lookup"><span data-stu-id="87fc2-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="87fc2-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="87fc2-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="87fc2-117">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="87fc2-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="87fc2-118">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren der nachverfolgung für einen Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="87fc2-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87fc2-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87fc2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="87fc2-120">Element</span><span class="sxs-lookup"><span data-stu-id="87fc2-120">Element</span></span>|<span data-ttu-id="87fc2-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87fc2-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87fc2-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87fc2-122">\<configuration></span></span>|<span data-ttu-id="87fc2-123">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="87fc2-123">The root element for all configuration elements in a .NET configuration file.</span></span>|

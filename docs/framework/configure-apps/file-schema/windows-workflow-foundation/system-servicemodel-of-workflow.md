---
title: <system.serviceModel> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151948"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="38d20-102">\<system.serviceModell> des Workflows</span><span class="sxs-lookup"><span data-stu-id="38d20-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="38d20-103">Dieser Konfigurationsabschnitt enthält alle Workflowkonfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="38d20-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="38d20-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38d20-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38d20-105">&nbsp;&nbsp;**\<System. ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="38d20-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d20-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="38d20-106">Syntax</span></span>  
  
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
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38d20-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38d20-107">Attributes and Elements</span></span>  
 <span data-ttu-id="38d20-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38d20-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38d20-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="38d20-109">Attributes</span></span>  
 <span data-ttu-id="38d20-110">Keine</span><span class="sxs-lookup"><span data-stu-id="38d20-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38d20-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38d20-111">Child Elements</span></span>  
  
|<span data-ttu-id="38d20-112">Element</span><span class="sxs-lookup"><span data-stu-id="38d20-112">Element</span></span>|<span data-ttu-id="38d20-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38d20-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38d20-114">\<Verhalten></span><span class="sxs-lookup"><span data-stu-id="38d20-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="38d20-115">In diesem Abschnitt wird die **serviceBehaviors-Auflistung** definiert.</span><span class="sxs-lookup"><span data-stu-id="38d20-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="38d20-116">Jedes Element der Auflistung definiert von Diensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="38d20-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="38d20-117">Jedes Verhaltenselement wird durch sein attribut eindeutiges **Name** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="38d20-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="38d20-118">\<Tracking-></span><span class="sxs-lookup"><span data-stu-id="38d20-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="38d20-119">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="38d20-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="38d20-120">Weitere Informationen zur Workflowverfolgung und deren Konfiguration finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren von Tracking für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="38d20-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38d20-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38d20-121">Parent Elements</span></span>  
  
|<span data-ttu-id="38d20-122">Element</span><span class="sxs-lookup"><span data-stu-id="38d20-122">Element</span></span>|<span data-ttu-id="38d20-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38d20-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38d20-124">\<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="38d20-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="38d20-125">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="38d20-125">The root element for all configuration elements in a .NET configuration file.</span></span>|

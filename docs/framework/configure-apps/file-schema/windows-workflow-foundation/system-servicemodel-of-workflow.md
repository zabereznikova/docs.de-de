---
title: < System. Service Model-> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 757a7a132a6e765e257097d251a110297c6a40bf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398598"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="f5d78-102">\<System. Service Model-> des Workflows</span><span class="sxs-lookup"><span data-stu-id="f5d78-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="f5d78-103">Dieser Konfigurationsabschnitt enthält alle Workflowkonfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="f5d78-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="f5d78-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5d78-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5d78-105">&nbsp;&nbsp; **\<Anlage. Service Model->**</span><span class="sxs-lookup"><span data-stu-id="f5d78-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d78-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5d78-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5d78-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f5d78-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f5d78-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5d78-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5d78-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f5d78-109">Attributes</span></span>  
 <span data-ttu-id="f5d78-110">None</span><span class="sxs-lookup"><span data-stu-id="f5d78-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5d78-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5d78-111">Child Elements</span></span>  
  
|<span data-ttu-id="f5d78-112">Element</span><span class="sxs-lookup"><span data-stu-id="f5d78-112">Element</span></span>|<span data-ttu-id="f5d78-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5d78-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5d78-114">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f5d78-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="f5d78-115">In diesem Abschnitt wird die serviceverhaltenauflistung definiert.</span><span class="sxs-lookup"><span data-stu-id="f5d78-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="f5d78-116">Jedes Element der Auflistung definiert von Diensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="f5d78-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="f5d78-117">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f5d78-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="f5d78-118">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f5d78-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="f5d78-119">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="f5d78-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="f5d78-120">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Überwachung und](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) -Ablauf Verfolgung und [Konfigurieren der Nachverfolgung für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f5d78-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5d78-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5d78-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f5d78-122">Element</span><span class="sxs-lookup"><span data-stu-id="f5d78-122">Element</span></span>|<span data-ttu-id="f5d78-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5d78-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5d78-124">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f5d78-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="f5d78-125">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f5d78-125">The root element for all configuration elements in a .NET configuration file.</span></span>|

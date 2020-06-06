---
title: <System. Service Model-> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151948"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="49c28-102">\<system.serviceModel>des Workflows</span><span class="sxs-lookup"><span data-stu-id="49c28-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="49c28-103">Dieser Konfigurationsabschnitt enthält alle Workflowkonfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="49c28-103">This configuration section contains all the workflow configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.ServiceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="49c28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49c28-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49c28-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="49c28-105">Attributes and Elements</span></span>  
 <span data-ttu-id="49c28-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49c28-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49c28-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="49c28-107">Attributes</span></span>  
 <span data-ttu-id="49c28-108">Keine</span><span class="sxs-lookup"><span data-stu-id="49c28-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49c28-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49c28-109">Child Elements</span></span>  
  
|<span data-ttu-id="49c28-110">Element</span><span class="sxs-lookup"><span data-stu-id="49c28-110">Element</span></span>|<span data-ttu-id="49c28-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49c28-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors-of-workflow.md)|<span data-ttu-id="49c28-112">In diesem Abschnitt wird **serviceBehaviors** die serviceverhaltenauflistung definiert.</span><span class="sxs-lookup"><span data-stu-id="49c28-112">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="49c28-113">Jedes Element der Auflistung definiert von Diensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="49c28-113">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="49c28-114">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="49c28-114">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[\<tracking>](tracking.md)|<span data-ttu-id="49c28-115">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="49c28-115">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="49c28-116">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Überwachung und](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) -Ablauf Verfolgung und [Konfigurieren der Nachverfolgung für einen Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="49c28-116">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49c28-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49c28-117">Parent Elements</span></span>  
  
|<span data-ttu-id="49c28-118">Element</span><span class="sxs-lookup"><span data-stu-id="49c28-118">Element</span></span>|<span data-ttu-id="49c28-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49c28-119">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="49c28-120">Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="49c28-120">The root element for all configuration elements in a .NET configuration file.</span></span>|

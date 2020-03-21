---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8985da7e1223ac117cf1b68227140634f9c85d3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151888"
---
# <a name="trackingprofile"></a><span data-ttu-id="9b3df-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9b3df-101">\<trackingProfile></span></span>
<span data-ttu-id="9b3df-102">Stellt einen Konfigurationsabschnitt zum Erstellen eines Abonnements von Workflownachverfolgungsdatensätzen für einen Nachverfolgungsteilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="9b3df-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="9b3df-103">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="9b3df-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="9b3df-104">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9b3df-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="9b3df-105">Weitere Informationen zur Workflowverfolgung und deren Konfiguration finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsprofile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9b3df-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9b3df-106">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b3df-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b3df-107">&nbsp;&nbsp;[**\<System. ServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b3df-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9b3df-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Tracking->**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9b3df-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9b3df-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span><span class="sxs-lookup"><span data-stu-id="9b3df-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3df-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b3df-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
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
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
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
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b3df-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b3df-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9b3df-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b3df-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b3df-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="9b3df-113">Attributes</span></span>  
  
|<span data-ttu-id="9b3df-114">attribute</span><span class="sxs-lookup"><span data-stu-id="9b3df-114">Attribute</span></span>|<span data-ttu-id="9b3df-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b3df-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b3df-116">name</span><span class="sxs-lookup"><span data-stu-id="9b3df-116">name</span></span>|<span data-ttu-id="9b3df-117">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="9b3df-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b3df-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b3df-118">Child Elements</span></span>  
  
|<span data-ttu-id="9b3df-119">Element</span><span class="sxs-lookup"><span data-stu-id="9b3df-119">Element</span></span>|<span data-ttu-id="9b3df-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b3df-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b3df-121">\<Teilnehmer></span><span class="sxs-lookup"><span data-stu-id="9b3df-121">\<participants></span></span>](participants.md)|<span data-ttu-id="9b3df-122">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9b3df-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b3df-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b3df-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9b3df-124">Element</span><span class="sxs-lookup"><span data-stu-id="9b3df-124">Element</span></span>|<span data-ttu-id="9b3df-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b3df-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b3df-126">\<Tracking-></span><span class="sxs-lookup"><span data-stu-id="9b3df-126">\<tracking></span></span>](tracking.md)|<span data-ttu-id="9b3df-127">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="9b3df-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b3df-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b3df-128">Remarks</span></span>  
 <span data-ttu-id="9b3df-129">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="9b3df-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="9b3df-130">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="9b3df-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="9b3df-131">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="9b3df-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="9b3df-132">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="9b3df-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="9b3df-133">Es gibt eine Handvoll Abfragetypen, mit denen <xref:System.Activities.Tracking.TrackingRecord> Sie verschiedene Klassen von Objekten abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="9b3df-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="9b3df-134">Eine vollständige Liste der [ \<](participants.md) Abfragen finden Sie unter Teilnehmer>und [Nachverfolgungsprofilen](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9b3df-134">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="9b3df-135">Das folgende Beispiel zeigt ein Überwachungsprofil in einer Konfigurationsdatei, `Started` `Completed` mit dem ein Nachverfolgungsteilnehmer die und die Workflowereignisse abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="9b3df-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b3df-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b3df-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="9b3df-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="9b3df-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9b3df-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="9b3df-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

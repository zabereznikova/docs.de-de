---
title: <trackingProfile>von WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: c5df03d63653e658a23a36e8943c06f156d2ae00
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854940"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="42ea2-102">\<TrackingProfile-> von WCF</span><span class="sxs-lookup"><span data-stu-id="42ea2-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="42ea2-103">Stellt einen Konfigurations Abschnitt zum Erstellen eines Abonnements für Workflow nach Verfolgungs Datensätze in einem nach Verfolgungs Teilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="42ea2-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="42ea2-104">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="42ea2-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="42ea2-105">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="42ea2-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
<span data-ttu-id="42ea2-106">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="42ea2-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="42ea2-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="42ea2-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="42ea2-108">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="42ea2-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="42ea2-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="42ea2-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="42ea2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="42ea2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="42ea2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<TrackingProfile->**</span><span class="sxs-lookup"><span data-stu-id="42ea2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ea2-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="42ea2-112">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String" />
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String">
              <arguments>
                <argument name="String" />
              </arguments>
              <states>
                <state name="String" />
              </states>
              <variables>
                <variable name="String" />
              </variables>
            </activityStateQuery>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestedQueries>
            <cancelRequestedQuery activityName="String"
                                  childActivityName="String" />
          </cancelRequestedQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String" />
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery faultSourceActivityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <stateMachineStateQueries>
            <stateMachineStateQuery activityName="String" />
          </stateMachineStateQueries>
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
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42ea2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42ea2-113">Attributes and Elements</span></span>  

<span data-ttu-id="42ea2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42ea2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42ea2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="42ea2-115">Attributes</span></span>  
  
|<span data-ttu-id="42ea2-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="42ea2-116">Attribute</span></span>|<span data-ttu-id="42ea2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42ea2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42ea2-118">NAME</span><span class="sxs-lookup"><span data-stu-id="42ea2-118">name</span></span>|<span data-ttu-id="42ea2-119">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="42ea2-119">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42ea2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42ea2-120">Child Elements</span></span>  
  
|<span data-ttu-id="42ea2-121">Element</span><span class="sxs-lookup"><span data-stu-id="42ea2-121">Element</span></span>|<span data-ttu-id="42ea2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42ea2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42ea2-123">\<participants></span><span class="sxs-lookup"><span data-stu-id="42ea2-123">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="42ea2-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="42ea2-124">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42ea2-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42ea2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="42ea2-126">Element</span><span class="sxs-lookup"><span data-stu-id="42ea2-126">Element</span></span>|<span data-ttu-id="42ea2-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42ea2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42ea2-128">\<tracking></span><span class="sxs-lookup"><span data-stu-id="42ea2-128">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="42ea2-129">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="42ea2-129">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42ea2-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42ea2-130">Remarks</span></span>  
 <span data-ttu-id="42ea2-131">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="42ea2-131">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="42ea2-132">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="42ea2-132">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="42ea2-133">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="42ea2-133">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="42ea2-134">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="42ea2-134">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="42ea2-135">Es gibt eine Handvoll Abfrage Typen, mit denen Sie verschiedene <xref:System.Activities.Tracking.TrackingRecord> Objektklassen abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="42ea2-135">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="42ea2-136">Eine umfassende Liste der Abfragen finden [ \<Sie unter Teilnehmer >](../windows-workflow-foundation/participants.md) -und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="42ea2-136">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="42ea2-137">Das folgende Beispiel zeigt ein Überwachungs Profil in einer Konfigurationsdatei, das es einem Überwachungs Teilnehmer ermöglicht, die `Started` - `Completed` und-Workflow Ereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="42ea2-137">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started" />
                <state name="Completed" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="42ea2-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42ea2-138">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="42ea2-139">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="42ea2-139">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="42ea2-140">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="42ea2-140">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

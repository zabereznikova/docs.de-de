---
title: <trackingProfile>von WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 79326322eeed1f6b73729da675eb02fe6de670df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932348"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="c8967-102">\<TrackingProfile-> von WCF</span><span class="sxs-lookup"><span data-stu-id="c8967-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="c8967-103">Stellt einen Konfigurations Abschnitt zum Erstellen eines Abonnements für Workflow nach Verfolgungs Datensätze in einem nach Verfolgungs Teilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="c8967-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="c8967-104">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="c8967-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="c8967-105">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c8967-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="c8967-106">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c8967-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="c8967-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c8967-107">\<system.serviceModel></span></span>  
<span data-ttu-id="c8967-108">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="c8967-108">\<tracking></span></span>  
<span data-ttu-id="c8967-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c8967-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8967-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8967-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8967-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8967-111">Attributes and Elements</span></span>  

<span data-ttu-id="c8967-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8967-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8967-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8967-113">Attributes</span></span>  
  
|<span data-ttu-id="c8967-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c8967-114">Attribute</span></span>|<span data-ttu-id="c8967-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8967-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8967-116">Name</span><span class="sxs-lookup"><span data-stu-id="c8967-116">name</span></span>|<span data-ttu-id="c8967-117">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="c8967-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8967-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8967-118">Child Elements</span></span>  
  
|<span data-ttu-id="c8967-119">Element</span><span class="sxs-lookup"><span data-stu-id="c8967-119">Element</span></span>|<span data-ttu-id="c8967-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8967-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8967-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="c8967-121">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="c8967-122">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c8967-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8967-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8967-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c8967-124">Element</span><span class="sxs-lookup"><span data-stu-id="c8967-124">Element</span></span>|<span data-ttu-id="c8967-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8967-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8967-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c8967-126">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="c8967-127">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="c8967-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8967-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8967-128">Remarks</span></span>  
 <span data-ttu-id="c8967-129">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="c8967-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="c8967-130">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="c8967-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="c8967-131">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="c8967-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="c8967-132">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="c8967-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="c8967-133">Es gibt eine Handvoll Abfrage Typen, mit denen Sie verschiedene <xref:System.Activities.Tracking.TrackingRecord> Objektklassen abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="c8967-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="c8967-134">Eine umfassende Liste der Abfragen finden [ \<Sie unter Teilnehmer >](../windows-workflow-foundation/participants.md) -und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c8967-134">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="c8967-135">Das folgende Beispiel zeigt ein Überwachungs Profil in einer Konfigurationsdatei, das es einem Überwachungs Teilnehmer ermöglicht, die `Started` - `Completed` und-Workflow Ereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="c8967-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8967-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8967-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="c8967-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c8967-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c8967-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c8967-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

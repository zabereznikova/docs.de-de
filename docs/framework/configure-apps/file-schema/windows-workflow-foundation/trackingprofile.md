---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8b8cfe95a646563642e7425fdb4b5257cafa466f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947303"
---
# <a name="trackingprofile"></a><span data-ttu-id="1dc0b-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1dc0b-101">\<trackingProfile></span></span>
<span data-ttu-id="1dc0b-102">Stellt einen Konfigurations Abschnitt zum Erstellen eines Abonnements für Workflow nach Verfolgungs Datensätze in einem nach Verfolgungs Teilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="1dc0b-103">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="1dc0b-104">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="1dc0b-105">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1dc0b-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1dc0b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1dc0b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1dc0b-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="1dc0b-107">\<tracking></span></span>  
<span data-ttu-id="1dc0b-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1dc0b-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc0b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1dc0b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dc0b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1dc0b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1dc0b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dc0b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1dc0b-112">Attributes</span></span>  
  
|<span data-ttu-id="1dc0b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1dc0b-113">Attribute</span></span>|<span data-ttu-id="1dc0b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dc0b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dc0b-115">Name</span><span class="sxs-lookup"><span data-stu-id="1dc0b-115">name</span></span>|<span data-ttu-id="1dc0b-116">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dc0b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dc0b-117">Child Elements</span></span>  
  
|<span data-ttu-id="1dc0b-118">Element</span><span class="sxs-lookup"><span data-stu-id="1dc0b-118">Element</span></span>|<span data-ttu-id="1dc0b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dc0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc0b-120">\<participants></span><span class="sxs-lookup"><span data-stu-id="1dc0b-120">\<participants></span></span>](participants.md)|<span data-ttu-id="1dc0b-121">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dc0b-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1dc0b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1dc0b-123">Element</span><span class="sxs-lookup"><span data-stu-id="1dc0b-123">Element</span></span>|<span data-ttu-id="1dc0b-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dc0b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc0b-125">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1dc0b-125">\<tracking></span></span>](tracking.md)|<span data-ttu-id="1dc0b-126">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dc0b-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1dc0b-127">Remarks</span></span>  
 <span data-ttu-id="1dc0b-128">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="1dc0b-129">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="1dc0b-130">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="1dc0b-131">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="1dc0b-132">Es gibt eine Handvoll Abfrage Typen, mit denen Sie verschiedene <xref:System.Activities.Tracking.TrackingRecord> Objektklassen abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="1dc0b-133">Eine umfassende Liste der Abfragen finden [ \<Sie unter Teilnehmer >](participants.md) -und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1dc0b-133">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="1dc0b-134">Das folgende Beispiel zeigt ein Überwachungs Profil in einer Konfigurationsdatei, das es einem Überwachungs Teilnehmer ermöglicht, die `Started` - `Completed` und-Workflow Ereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="1dc0b-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1dc0b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dc0b-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="1dc0b-136">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1dc0b-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1dc0b-137">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1dc0b-137">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;trackingProfile&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: fe8d129769d0948160d581aa578b5ac2d0dc0e4d
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087647"
---
# <a name="lttrackingprofilegt"></a><span data-ttu-id="e7147-102">&lt;trackingProfile&gt;</span><span class="sxs-lookup"><span data-stu-id="e7147-102">&lt;trackingProfile&gt;</span></span>
<span data-ttu-id="e7147-103">Stellt einen Konfigurationsabschnitt zum Erstellen eines Abonnements für Workflow-Verfolgungsdatensätze in einen Nachverfolgungsteilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="e7147-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="e7147-104">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="e7147-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="e7147-105">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7147-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="e7147-106">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e7147-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e7147-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e7147-107">\<system.serviceModel></span></span>  
<span data-ttu-id="e7147-108">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="e7147-108">\<tracking></span></span>  
<span data-ttu-id="e7147-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e7147-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7147-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7147-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7147-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e7147-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7147-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7147-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7147-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7147-113">Attributes</span></span>  
  
|<span data-ttu-id="e7147-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e7147-114">Attribute</span></span>|<span data-ttu-id="e7147-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7147-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7147-116">Name</span><span class="sxs-lookup"><span data-stu-id="e7147-116">name</span></span>|<span data-ttu-id="e7147-117">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="e7147-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7147-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7147-118">Child Elements</span></span>  
  
|<span data-ttu-id="e7147-119">Element</span><span class="sxs-lookup"><span data-stu-id="e7147-119">Element</span></span>|<span data-ttu-id="e7147-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7147-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7147-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="e7147-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="e7147-122">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e7147-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7147-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7147-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e7147-124">Element</span><span class="sxs-lookup"><span data-stu-id="e7147-124">Element</span></span>|<span data-ttu-id="e7147-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7147-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7147-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e7147-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="e7147-127">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="e7147-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7147-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7147-128">Remarks</span></span>  
 <span data-ttu-id="e7147-129">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="e7147-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="e7147-130">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="e7147-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="e7147-131">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="e7147-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="e7147-132">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="e7147-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="e7147-133">Es gibt eine Handvoll Abfragetypen, mit denen Sie andere Klassen von abonnieren <xref:System.Activities.Tracking.TrackingRecord> Objekte.</span><span class="sxs-lookup"><span data-stu-id="e7147-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="e7147-134">Eine vollständige Liste der Abfragen, finden Sie unter [ \<Teilnehmer >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="e7147-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="e7147-135">Das folgende Beispiel zeigt das Überwachungsprofil in einer Konfigurationsdatei, die einen Überwachungsteilnehmer abonniert ermöglicht die `Started` und `Completed` Workflowereignisse.</span><span class="sxs-lookup"><span data-stu-id="e7147-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e7147-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7147-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="e7147-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e7147-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e7147-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="e7147-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

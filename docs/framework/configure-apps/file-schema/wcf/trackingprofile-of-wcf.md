---
title: '&lt;trackingProfile&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 34497c8e27f56adce12fa358620d3d3f8fe54e48
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532112"
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="c9d0b-102">&lt;trackingProfile&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="c9d0b-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="c9d0b-103">Stellt einen Konfigurationsabschnitt zum Erstellen eines Abonnements für Workflow-Verfolgungsdatensätze in einen Nachverfolgungsteilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="c9d0b-104">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="c9d0b-105">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="c9d0b-106">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c9d0b-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="c9d0b-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c9d0b-107">\<system.serviceModel></span></span>  
<span data-ttu-id="c9d0b-108">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="c9d0b-108">\<tracking></span></span>  
<span data-ttu-id="c9d0b-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c9d0b-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d0b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9d0b-110">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>      <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>    
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9d0b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9d0b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c9d0b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9d0b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9d0b-113">Attributes</span></span>  
  
|<span data-ttu-id="c9d0b-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c9d0b-114">Attribute</span></span>|<span data-ttu-id="c9d0b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9d0b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9d0b-116">Name</span><span class="sxs-lookup"><span data-stu-id="c9d0b-116">name</span></span>|<span data-ttu-id="c9d0b-117">Eine Zeichenfolge, die den Namen des Nachverfolgungsprofils angibt.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9d0b-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9d0b-118">Child Elements</span></span>  
  
|<span data-ttu-id="c9d0b-119">Element</span><span class="sxs-lookup"><span data-stu-id="c9d0b-119">Element</span></span>|<span data-ttu-id="c9d0b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9d0b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9d0b-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="c9d0b-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="c9d0b-122">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-122">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9d0b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9d0b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c9d0b-124">Element</span><span class="sxs-lookup"><span data-stu-id="c9d0b-124">Element</span></span>|<span data-ttu-id="c9d0b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9d0b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9d0b-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c9d0b-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="c9d0b-127">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9d0b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9d0b-128">Remarks</span></span>  
 <span data-ttu-id="c9d0b-129">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="c9d0b-130">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="c9d0b-131">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="c9d0b-132">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="c9d0b-133">Es gibt eine Handvoll Abfragetypen, mit denen Sie andere Klassen von abonnieren <xref:System.Activities.Tracking.TrackingRecord> Objekte.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="c9d0b-134">Eine vollständige Liste der Abfragen, finden Sie unter [ \<Teilnehmer >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="c9d0b-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="c9d0b-135">Das folgende Beispiel zeigt das Überwachungsprofil in einer Konfigurationsdatei, die einen Überwachungsteilnehmer abonniert ermöglicht die `Started` und `Completed` Workflowereignisse.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9d0b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9d0b-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="c9d0b-137">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c9d0b-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c9d0b-138">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c9d0b-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

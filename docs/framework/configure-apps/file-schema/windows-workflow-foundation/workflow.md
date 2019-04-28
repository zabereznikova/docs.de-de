---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: d6c23bb0b819b5f22367a93db0dec64787449664
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613481"
---
# <a name="workflow"></a><span data-ttu-id="cd2a1-101">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cd2a1-101">\<workflow></span></span>
<span data-ttu-id="cd2a1-102">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="cd2a1-103">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cd2a1-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="cd2a1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cd2a1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cd2a1-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="cd2a1-105">\<tracking></span></span>  
<span data-ttu-id="cd2a1-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cd2a1-106">\<trackingProfile></span></span>  
<span data-ttu-id="cd2a1-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cd2a1-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd2a1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd2a1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd2a1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd2a1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cd2a1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd2a1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd2a1-111">Attributes</span></span>  
  
|<span data-ttu-id="cd2a1-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd2a1-112">Attribute</span></span>|<span data-ttu-id="cd2a1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd2a1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd2a1-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="cd2a1-114">activityDefinitionId</span></span>|<span data-ttu-id="cd2a1-115">Eine Zeichenfolge, die die Aktivitätsdefinitions-ID des Workflows angibt, der nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd2a1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd2a1-116">Child Elements</span></span>  
  
|<span data-ttu-id="cd2a1-117">Element</span><span class="sxs-lookup"><span data-stu-id="cd2a1-117">Element</span></span>|<span data-ttu-id="cd2a1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd2a1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd2a1-119">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-119">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="cd2a1-120">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="cd2a1-121">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="cd2a1-122">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-122">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="cd2a1-123">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="cd2a1-124">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="cd2a1-125">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="cd2a1-126">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="cd2a1-127">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-127">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="cd2a1-128">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="cd2a1-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="cd2a1-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-130">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="cd2a1-131">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="cd2a1-132">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="cd2a1-133">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-133">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="cd2a1-134">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="cd2a1-135">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="cd2a1-136">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-136">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="cd2a1-137">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cd2a1-138">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="cd2a1-139">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="cd2a1-140">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="cd2a1-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="cd2a1-141">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="cd2a1-142">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd2a1-143">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd2a1-143">Parent Elements</span></span>  
  
|<span data-ttu-id="cd2a1-144">Element</span><span class="sxs-lookup"><span data-stu-id="cd2a1-144">Element</span></span>|<span data-ttu-id="cd2a1-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd2a1-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd2a1-146">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cd2a1-146">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="cd2a1-147">Stellt einen Konfigurationsabschnitt zum Erstellen eines Abonnements für Workflow-Verfolgungsdatensätze in einen Nachverfolgungsteilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="cd2a1-148">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="cd2a1-149">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd2a1-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd2a1-150">Remarks</span></span>  
 <span data-ttu-id="cd2a1-151">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer bestimmten Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="cd2a1-152">Dieses Konfigurationselement gibt die nachzuverfolgende Workflowinstanz an.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="cd2a1-153">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="cd2a1-154">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="cd2a1-155">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="cd2a1-156">Es gibt eine Handvoll Abfragetypen, die es, dass Sie andere Klassen ermöglichen von nachverfolgungsdatensätzen abonnieren.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="cd2a1-157">Eine vollständige Liste der Abfragen, finden Sie unter der untergeordneten Elementliste dieses Themas und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cd2a1-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="cd2a1-158">Das folgende Beispiel zeigt das Überwachungsprofil in einer Konfigurationsdatei, die einen Überwachungsteilnehmer abonniert ermöglicht die `Started` und `Completed` Workflowereignisse.</span><span class="sxs-lookup"><span data-stu-id="cd2a1-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd2a1-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd2a1-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="cd2a1-160">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="cd2a1-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cd2a1-161">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="cd2a1-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

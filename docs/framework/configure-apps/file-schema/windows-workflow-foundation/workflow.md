---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 89f9d0e7c57f6e66b9fdffd148d9dcae5a189fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947235"
---
# <a name="workflow"></a><span data-ttu-id="1c88f-101">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1c88f-101">\<workflow></span></span>
<span data-ttu-id="1c88f-102">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="1c88f-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="1c88f-103">Weitere Informationen zur Workflow Überwachung und deren Konfiguration finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1c88f-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1c88f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1c88f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1c88f-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="1c88f-105">\<tracking></span></span>  
<span data-ttu-id="1c88f-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1c88f-106">\<trackingProfile></span></span>  
<span data-ttu-id="1c88f-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1c88f-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c88f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c88f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c88f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1c88f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c88f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1c88f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c88f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c88f-111">Attributes</span></span>  
  
|<span data-ttu-id="1c88f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="1c88f-112">Attribute</span></span>|<span data-ttu-id="1c88f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c88f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c88f-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="1c88f-114">activityDefinitionId</span></span>|<span data-ttu-id="1c88f-115">Eine Zeichenfolge, die die Aktivitätsdefinitions-ID des Workflows angibt, der nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="1c88f-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c88f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c88f-116">Child Elements</span></span>  
  
|<span data-ttu-id="1c88f-117">Element</span><span class="sxs-lookup"><span data-stu-id="1c88f-117">Element</span></span>|<span data-ttu-id="1c88f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c88f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c88f-119">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-119">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="1c88f-120">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="1c88f-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1c88f-121">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="1c88f-122">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-122">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="1c88f-123">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="1c88f-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="1c88f-124">Beispielsweise können Sie nachverfolgen, wann die "E-Mail senden"-Aktivität innerhalb einer Workflow Instanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="1c88f-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="1c88f-125">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="1c88f-126">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="1c88f-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="1c88f-127">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-127">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="1c88f-128">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="1c88f-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1c88f-129">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="1c88f-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-130">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="1c88f-131">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="1c88f-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1c88f-132">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="1c88f-133">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-133">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="1c88f-134">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="1c88f-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1c88f-135">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="1c88f-136">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-136">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="1c88f-137">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="1c88f-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1c88f-138">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1c88f-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1c88f-139">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="1c88f-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1c88f-140">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1c88f-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="1c88f-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="1c88f-141">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="1c88f-142">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1c88f-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c88f-143">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c88f-143">Parent Elements</span></span>  
  
|<span data-ttu-id="1c88f-144">Element</span><span class="sxs-lookup"><span data-stu-id="1c88f-144">Element</span></span>|<span data-ttu-id="1c88f-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c88f-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c88f-146">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1c88f-146">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="1c88f-147">Stellt einen Konfigurations Abschnitt zum Erstellen eines Abonnements für Workflow nach Verfolgungs Datensätze in einem nach Verfolgungs Teilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="1c88f-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="1c88f-148">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="1c88f-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="1c88f-149">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1c88f-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c88f-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c88f-150">Remarks</span></span>  
 <span data-ttu-id="1c88f-151">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer bestimmten Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="1c88f-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="1c88f-152">Dieses Konfigurationselement gibt die nachzuverfolgende Workflowinstanz an.</span><span class="sxs-lookup"><span data-stu-id="1c88f-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="1c88f-153">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="1c88f-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="1c88f-154">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="1c88f-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="1c88f-155">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="1c88f-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="1c88f-156">Es gibt eine Handvoll Abfrage Typen, mit denen Sie verschiedene Klassen von nach Verfolgungs Datensätzen abonnieren können.</span><span class="sxs-lookup"><span data-stu-id="1c88f-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="1c88f-157">Eine umfassende Liste der Abfragen finden Sie in der Liste der untergeordneten Elemente dieses Themas und der [Überwachungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1c88f-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="1c88f-158">Das folgende Beispiel zeigt ein Überwachungs Profil in einer Konfigurationsdatei, das es einem Überwachungs Teilnehmer ermöglicht, die `Started` - `Completed` und-Workflow Ereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="1c88f-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c88f-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c88f-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="1c88f-160">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1c88f-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1c88f-161">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1c88f-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

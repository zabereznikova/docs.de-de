---
title: '&lt;workflow&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 940d396bd6e3dc3cdc5d8fb6f72d293061f3aa0e
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326490"
---
# <a name="ltworkflowgt"></a><span data-ttu-id="db68c-102">&lt;workflow&gt;</span><span class="sxs-lookup"><span data-stu-id="db68c-102">&lt;workflow&gt;</span></span>
<span data-ttu-id="db68c-103">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="db68c-103">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="db68c-104">Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="db68c-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="db68c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="db68c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="db68c-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="db68c-106">\<tracking></span></span>  
<span data-ttu-id="db68c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="db68c-107">\<trackingProfile></span></span>  
<span data-ttu-id="db68c-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="db68c-108">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db68c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="db68c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db68c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db68c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db68c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db68c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db68c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="db68c-112">Attributes</span></span>  
  
|<span data-ttu-id="db68c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="db68c-113">Attribute</span></span>|<span data-ttu-id="db68c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db68c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db68c-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="db68c-115">activityDefinitionId</span></span>|<span data-ttu-id="db68c-116">Eine Zeichenfolge, die die Aktivitätsdefinitions-ID des Workflows angibt, der nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="db68c-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db68c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db68c-117">Child Elements</span></span>  
  
|<span data-ttu-id="db68c-118">Element</span><span class="sxs-lookup"><span data-stu-id="db68c-118">Element</span></span>|<span data-ttu-id="db68c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db68c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db68c-120">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-120">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="db68c-121">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="db68c-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="db68c-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="db68c-123">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-123">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="db68c-124">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="db68c-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="db68c-125">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="db68c-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="db68c-126">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="db68c-127">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="db68c-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="db68c-128">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-128">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="db68c-129">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="db68c-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="db68c-130">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="db68c-131">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-131">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="db68c-132">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Anforderungen nachzuverfolgen, mit denen die übergeordnete Aktivität den Abbruch einer untergeordneten Aktivität verlangt.</span><span class="sxs-lookup"><span data-stu-id="db68c-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="db68c-133">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="db68c-134">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-134">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="db68c-135">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="db68c-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="db68c-136">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="db68c-137">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-137">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="db68c-138">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Behandlung von Fehlern nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="db68c-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="db68c-139">Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="db68c-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="db68c-140">Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten.</span><span class="sxs-lookup"><span data-stu-id="db68c-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="db68c-141">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="db68c-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="db68c-142">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="db68c-142">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="db68c-143">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="db68c-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db68c-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db68c-144">Parent Elements</span></span>  
  
|<span data-ttu-id="db68c-145">Element</span><span class="sxs-lookup"><span data-stu-id="db68c-145">Element</span></span>|<span data-ttu-id="db68c-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db68c-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db68c-147">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="db68c-147">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="db68c-148">Stellt einen Konfigurationsabschnitt zum Erstellen eines Abonnements für Workflow-Verfolgungsdatensätze in einen Nachverfolgungsteilnehmer dar.</span><span class="sxs-lookup"><span data-stu-id="db68c-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="db68c-149">Ein Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="db68c-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="db68c-150">Die innerhalb des Nachverfolgungsprofilabschnitts definierten Abfragen geben die Art von Ereignissen an, die das Abonnement zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="db68c-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db68c-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db68c-151">Remarks</span></span>  
 <span data-ttu-id="db68c-152">Überwachungsprofile enthalten Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer bestimmten Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="db68c-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="db68c-153">Dieses Konfigurationselement gibt die nachzuverfolgende Workflowinstanz an.</span><span class="sxs-lookup"><span data-stu-id="db68c-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="db68c-154">Je nach Überwachungsanforderungen können Sie ein Profil schreiben, das sehr grob gehalten ist und einen kleinen Satz von unspezifischen Zustandsänderungen eines Workflows abonniert.</span><span class="sxs-lookup"><span data-stu-id="db68c-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="db68c-155">Umgekehrt ist es möglich, ein sehr spezifisches Profil zu erstellen, dessen resultierende Ereignisse umfangreich genug sind, um später einen genauen Ausführungsfluss zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="db68c-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="db68c-156">Überwachungsprofile werden als deklarative Abonnements für Überwachungsdatensätze angeordnet, die es Ihnen ermöglichen, bestimmte Überwachungsdatensätze aus der Workflowlaufzeit abzufragen.</span><span class="sxs-lookup"><span data-stu-id="db68c-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="db68c-157">Es gibt eine Handvoll Abfragetypen, die es, dass Sie andere Klassen ermöglichen von nachverfolgungsdatensätzen abonnieren.</span><span class="sxs-lookup"><span data-stu-id="db68c-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="db68c-158">Eine vollständige Liste der Abfragen, finden Sie unter der untergeordneten Elementliste dieses Themas und [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="db68c-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="db68c-159">Das folgende Beispiel zeigt das Überwachungsprofil in einer Konfigurationsdatei, die einen Überwachungsteilnehmer abonniert ermöglicht die `Started` und `Completed` Workflowereignisse.</span><span class="sxs-lookup"><span data-stu-id="db68c-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="db68c-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db68c-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="db68c-161">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="db68c-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="db68c-162">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="db68c-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

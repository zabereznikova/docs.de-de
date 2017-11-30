---
title: "&lt;Zustände&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 73848bd1b8b23d6135572dc7fbb7b5e15b169554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="94986-102">&lt;Zustände&gt;</span><span class="sxs-lookup"><span data-stu-id="94986-102">&lt;states&gt;</span></span>
<span data-ttu-id="94986-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="94986-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="94986-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="94986-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="94986-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="94986-105">\<system.serviceModel></span></span>  
<span data-ttu-id="94986-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="94986-106">\<tracking></span></span>  
<span data-ttu-id="94986-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="94986-107">\<trackingProfile></span></span>  
<span data-ttu-id="94986-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="94986-108">\<workflow></span></span>  
<span data-ttu-id="94986-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="94986-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="94986-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="94986-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="94986-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="94986-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94986-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="94986-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94986-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="94986-113">Attributes and Elements</span></span>  
 <span data-ttu-id="94986-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94986-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94986-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="94986-115">Attributes</span></span>  
 <span data-ttu-id="94986-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="94986-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94986-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94986-117">Child Elements</span></span>  
  
|<span data-ttu-id="94986-118">Element</span><span class="sxs-lookup"><span data-stu-id="94986-118">Element</span></span>|<span data-ttu-id="94986-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94986-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94986-120">\<State ></span><span class="sxs-lookup"><span data-stu-id="94986-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="94986-121">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94986-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94986-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94986-122">Parent Elements</span></span>  
  
|<span data-ttu-id="94986-123">Element</span><span class="sxs-lookup"><span data-stu-id="94986-123">Element</span></span>|<span data-ttu-id="94986-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94986-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94986-125">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="94986-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="94986-126">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="94986-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94986-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94986-127">Remarks</span></span>  
 <span data-ttu-id="94986-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="94986-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="94986-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="94986-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="94986-130">Zustand</span><span class="sxs-lookup"><span data-stu-id="94986-130">State</span></span>|<span data-ttu-id="94986-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94986-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94986-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="94986-132">Aborted</span></span>|<span data-ttu-id="94986-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="94986-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="94986-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="94986-134">Completed</span></span>|<span data-ttu-id="94986-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="94986-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="94986-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="94986-136">Deleted</span></span>|<span data-ttu-id="94986-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="94986-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="94986-138">Idle</span><span class="sxs-lookup"><span data-stu-id="94986-138">Idle</span></span>|<span data-ttu-id="94986-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="94986-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="94986-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="94986-140">Persisted</span></span>|<span data-ttu-id="94986-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="94986-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="94986-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="94986-142">Resumed</span></span>|<span data-ttu-id="94986-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="94986-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="94986-144">Started</span><span class="sxs-lookup"><span data-stu-id="94986-144">Started</span></span>|<span data-ttu-id="94986-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="94986-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="94986-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="94986-146">UnhandledException</span></span>|<span data-ttu-id="94986-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94986-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="94986-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="94986-148">Unloaded</span></span>|<span data-ttu-id="94986-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="94986-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="94986-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="94986-150">Canceled</span></span>|<span data-ttu-id="94986-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="94986-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="94986-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="94986-152">Suspended</span></span>|<span data-ttu-id="94986-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="94986-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="94986-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="94986-154">Terminated</span></span>|<span data-ttu-id="94986-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="94986-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="94986-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="94986-156">Unsuspended</span></span>|<span data-ttu-id="94986-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="94986-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94986-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94986-158">Example</span></span>  
 <span data-ttu-id="94986-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="94986-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94986-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94986-160">See Also</span></span>  
 <span data-ttu-id="94986-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94986-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="94986-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94986-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="94986-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94986-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="94986-164">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="94986-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="94986-165">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="94986-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;state&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca170740fbe55547c9897054f9c4782c2d25afdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt"></a><span data-ttu-id="e0451-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="e0451-102">&lt;state&gt;</span></span>
<span data-ttu-id="e0451-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="e0451-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e0451-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e0451-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e0451-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e0451-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e0451-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="e0451-106">\<tracking></span></span>  
<span data-ttu-id="e0451-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e0451-107">\<trackingProfile></span></span>  
<span data-ttu-id="e0451-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="e0451-108">\<workflow></span></span>  
<span data-ttu-id="e0451-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e0451-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e0451-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e0451-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="e0451-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="e0451-111">\<states></span></span>  
<span data-ttu-id="e0451-112">\<State ></span><span class="sxs-lookup"><span data-stu-id="e0451-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0451-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0451-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0451-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0451-114">Attributes and Elements</span></span>  
 <span data-ttu-id="e0451-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0451-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0451-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0451-116">Attributes</span></span>  
  
|<span data-ttu-id="e0451-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="e0451-117">Attribute</span></span>|<span data-ttu-id="e0451-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0451-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0451-119">Name</span><span class="sxs-lookup"><span data-stu-id="e0451-119">name</span></span>|<span data-ttu-id="e0451-120">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="e0451-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0451-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0451-121">Child Elements</span></span>  
 <span data-ttu-id="e0451-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e0451-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0451-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0451-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e0451-124">Element</span><span class="sxs-lookup"><span data-stu-id="e0451-124">Element</span></span>|<span data-ttu-id="e0451-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0451-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0451-126">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="e0451-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="e0451-127">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="e0451-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0451-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0451-128">Remarks</span></span>  
 <span data-ttu-id="e0451-129">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="e0451-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e0451-130">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0451-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e0451-131">Zustand</span><span class="sxs-lookup"><span data-stu-id="e0451-131">State</span></span>|<span data-ttu-id="e0451-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0451-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0451-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="e0451-133">Aborted</span></span>|<span data-ttu-id="e0451-134">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="e0451-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e0451-135">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="e0451-135">Completed</span></span>|<span data-ttu-id="e0451-136">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e0451-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e0451-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="e0451-137">Deleted</span></span>|<span data-ttu-id="e0451-138">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e0451-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e0451-139">Idle</span><span class="sxs-lookup"><span data-stu-id="e0451-139">Idle</span></span>|<span data-ttu-id="e0451-140">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="e0451-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e0451-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="e0451-141">Persisted</span></span>|<span data-ttu-id="e0451-142">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e0451-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e0451-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="e0451-143">Resumed</span></span>|<span data-ttu-id="e0451-144">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="e0451-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e0451-145">Started</span><span class="sxs-lookup"><span data-stu-id="e0451-145">Started</span></span>|<span data-ttu-id="e0451-146">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="e0451-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e0451-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e0451-147">UnhandledException</span></span>|<span data-ttu-id="e0451-148">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e0451-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e0451-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="e0451-149">Unloaded</span></span>|<span data-ttu-id="e0451-150">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="e0451-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e0451-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="e0451-151">Canceled</span></span>|<span data-ttu-id="e0451-152">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="e0451-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e0451-153">Angehalten</span><span class="sxs-lookup"><span data-stu-id="e0451-153">Suspended</span></span>|<span data-ttu-id="e0451-154">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="e0451-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e0451-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="e0451-155">Terminated</span></span>|<span data-ttu-id="e0451-156">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="e0451-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e0451-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="e0451-157">Unsuspended</span></span>|<span data-ttu-id="e0451-158">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e0451-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0451-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0451-159">Example</span></span>  
 <span data-ttu-id="e0451-160">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="e0451-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0451-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0451-161">See Also</span></span>  
 <span data-ttu-id="e0451-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e0451-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e0451-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e0451-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e0451-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e0451-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="e0451-165">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="e0451-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e0451-166">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="e0451-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

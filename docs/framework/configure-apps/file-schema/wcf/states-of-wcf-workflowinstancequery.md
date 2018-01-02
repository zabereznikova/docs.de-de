---
title: '&lt;states&gt; von WCF, &lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5995ebfc2cee0f636d2acd8b1cadead0bc7b67e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="d7797-102">&lt;states&gt; von WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d7797-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="d7797-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="d7797-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d7797-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d7797-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="d7797-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d7797-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d7797-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="d7797-106">\<tracking></span></span>  
<span data-ttu-id="d7797-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d7797-107">\<trackingProfile></span></span>  
<span data-ttu-id="d7797-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="d7797-108">\<workflow></span></span>  
<span data-ttu-id="d7797-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="d7797-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="d7797-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d7797-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="d7797-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="d7797-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7797-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7797-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7797-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7797-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d7797-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7797-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7797-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7797-115">Attributes</span></span>  
 <span data-ttu-id="d7797-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d7797-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7797-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7797-117">Child Elements</span></span>  
  
|<span data-ttu-id="d7797-118">Element</span><span class="sxs-lookup"><span data-stu-id="d7797-118">Element</span></span>|<span data-ttu-id="d7797-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7797-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7797-120">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="d7797-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="d7797-121">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d7797-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7797-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7797-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d7797-123">Element</span><span class="sxs-lookup"><span data-stu-id="d7797-123">Element</span></span>|<span data-ttu-id="d7797-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7797-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7797-125">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="d7797-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="d7797-126">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d7797-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7797-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7797-127">Remarks</span></span>  
 <span data-ttu-id="d7797-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="d7797-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="d7797-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d7797-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="d7797-130">Zustand</span><span class="sxs-lookup"><span data-stu-id="d7797-130">State</span></span>|<span data-ttu-id="d7797-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7797-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7797-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="d7797-132">Aborted</span></span>|<span data-ttu-id="d7797-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d7797-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d7797-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="d7797-134">Completed</span></span>|<span data-ttu-id="d7797-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d7797-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d7797-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="d7797-136">Deleted</span></span>|<span data-ttu-id="d7797-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d7797-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d7797-138">Idle</span><span class="sxs-lookup"><span data-stu-id="d7797-138">Idle</span></span>|<span data-ttu-id="d7797-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="d7797-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d7797-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="d7797-140">Persisted</span></span>|<span data-ttu-id="d7797-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d7797-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d7797-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="d7797-142">Resumed</span></span>|<span data-ttu-id="d7797-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="d7797-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d7797-144">Started</span><span class="sxs-lookup"><span data-stu-id="d7797-144">Started</span></span>|<span data-ttu-id="d7797-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="d7797-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d7797-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d7797-146">UnhandledException</span></span>|<span data-ttu-id="d7797-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d7797-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d7797-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="d7797-148">Unloaded</span></span>|<span data-ttu-id="d7797-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="d7797-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d7797-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="d7797-150">Canceled</span></span>|<span data-ttu-id="d7797-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d7797-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d7797-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="d7797-152">Suspended</span></span>|<span data-ttu-id="d7797-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d7797-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d7797-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="d7797-154">Terminated</span></span>|<span data-ttu-id="d7797-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="d7797-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d7797-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="d7797-156">Unsuspended</span></span>|<span data-ttu-id="d7797-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d7797-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7797-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7797-158">Example</span></span>  
 <span data-ttu-id="d7797-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="d7797-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7797-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7797-160">See Also</span></span>  
 <span data-ttu-id="d7797-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d7797-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="d7797-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d7797-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="d7797-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d7797-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="d7797-164">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d7797-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d7797-165">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d7797-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

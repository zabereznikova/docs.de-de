---
title: '&lt;states&gt; von WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef3d8d05dad684b07ee527dbd34ae6269ae57657
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="edd7f-102">&lt;states&gt; von WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="edd7f-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="edd7f-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="edd7f-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="edd7f-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="edd7f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="edd7f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="edd7f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="edd7f-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="edd7f-106">\<tracking></span></span>  
<span data-ttu-id="edd7f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="edd7f-107">\<trackingProfile></span></span>  
<span data-ttu-id="edd7f-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="edd7f-108">\<workflow></span></span>  
<span data-ttu-id="edd7f-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="edd7f-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="edd7f-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="edd7f-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="edd7f-111">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="edd7f-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edd7f-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="edd7f-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edd7f-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="edd7f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="edd7f-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edd7f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edd7f-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="edd7f-115">Attributes</span></span>  
 <span data-ttu-id="edd7f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="edd7f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edd7f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edd7f-117">Child Elements</span></span>  
  
|<span data-ttu-id="edd7f-118">Element</span><span class="sxs-lookup"><span data-stu-id="edd7f-118">Element</span></span>|<span data-ttu-id="edd7f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edd7f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edd7f-120">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="edd7f-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="edd7f-121">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="edd7f-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edd7f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edd7f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="edd7f-123">Element</span><span class="sxs-lookup"><span data-stu-id="edd7f-123">Element</span></span>|<span data-ttu-id="edd7f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edd7f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edd7f-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="edd7f-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="edd7f-126">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="edd7f-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edd7f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edd7f-127">Remarks</span></span>  
 <span data-ttu-id="edd7f-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="edd7f-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="edd7f-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="edd7f-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="edd7f-130">Zustand</span><span class="sxs-lookup"><span data-stu-id="edd7f-130">State</span></span>|<span data-ttu-id="edd7f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edd7f-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="edd7f-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="edd7f-132">Aborted</span></span>|<span data-ttu-id="edd7f-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="edd7f-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="edd7f-134">Completed</span></span>|<span data-ttu-id="edd7f-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="edd7f-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="edd7f-136">Deleted</span></span>|<span data-ttu-id="edd7f-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="edd7f-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="edd7f-138">Idle</span><span class="sxs-lookup"><span data-stu-id="edd7f-138">Idle</span></span>|<span data-ttu-id="edd7f-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="edd7f-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="edd7f-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="edd7f-140">Persisted</span></span>|<span data-ttu-id="edd7f-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="edd7f-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="edd7f-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="edd7f-142">Resumed</span></span>|<span data-ttu-id="edd7f-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="edd7f-144">Started</span><span class="sxs-lookup"><span data-stu-id="edd7f-144">Started</span></span>|<span data-ttu-id="edd7f-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="edd7f-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="edd7f-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="edd7f-146">UnhandledException</span></span>|<span data-ttu-id="edd7f-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="edd7f-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="edd7f-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="edd7f-148">Unloaded</span></span>|<span data-ttu-id="edd7f-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="edd7f-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="edd7f-150">Canceled</span></span>|<span data-ttu-id="edd7f-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="edd7f-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="edd7f-152">Suspended</span></span>|<span data-ttu-id="edd7f-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="edd7f-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="edd7f-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="edd7f-154">Terminated</span></span>|<span data-ttu-id="edd7f-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="edd7f-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="edd7f-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="edd7f-156">Unsuspended</span></span>|<span data-ttu-id="edd7f-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="edd7f-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="edd7f-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="edd7f-158">Example</span></span>  
 <span data-ttu-id="edd7f-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="edd7f-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edd7f-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edd7f-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="edd7f-161">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="edd7f-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="edd7f-162">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="edd7f-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

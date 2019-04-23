---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073121"
---
# <a name="states"></a><span data-ttu-id="a7057-101">\<states></span><span class="sxs-lookup"><span data-stu-id="a7057-101">\<states></span></span>
<span data-ttu-id="a7057-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="a7057-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="a7057-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a7057-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a7057-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7057-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a7057-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a7057-105">\<tracking></span></span>  
<span data-ttu-id="a7057-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a7057-106">\<trackingProfile></span></span>  
<span data-ttu-id="a7057-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a7057-107">\<workflow></span></span>  
<span data-ttu-id="a7057-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a7057-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="a7057-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a7057-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="a7057-110">\<states></span><span class="sxs-lookup"><span data-stu-id="a7057-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7057-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7057-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7057-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7057-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a7057-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7057-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7057-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7057-114">Attributes</span></span>  
 <span data-ttu-id="a7057-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a7057-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7057-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7057-116">Child Elements</span></span>  
  
|<span data-ttu-id="a7057-117">Element</span><span class="sxs-lookup"><span data-stu-id="a7057-117">Element</span></span>|<span data-ttu-id="a7057-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7057-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7057-119">\<state></span><span class="sxs-lookup"><span data-stu-id="a7057-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="a7057-120">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a7057-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7057-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7057-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a7057-122">Element</span><span class="sxs-lookup"><span data-stu-id="a7057-122">Element</span></span>|<span data-ttu-id="a7057-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7057-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7057-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a7057-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="a7057-125">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a7057-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7057-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7057-126">Remarks</span></span>  
 <span data-ttu-id="a7057-127">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="a7057-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="a7057-128">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a7057-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="a7057-129">Zustand</span><span class="sxs-lookup"><span data-stu-id="a7057-129">State</span></span>|<span data-ttu-id="a7057-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7057-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7057-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="a7057-131">Aborted</span></span>|<span data-ttu-id="a7057-132">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a7057-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a7057-133">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="a7057-133">Completed</span></span>|<span data-ttu-id="a7057-134">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a7057-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="a7057-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="a7057-135">Deleted</span></span>|<span data-ttu-id="a7057-136">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a7057-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="a7057-137">Idle</span><span class="sxs-lookup"><span data-stu-id="a7057-137">Idle</span></span>|<span data-ttu-id="a7057-138">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="a7057-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="a7057-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="a7057-139">Persisted</span></span>|<span data-ttu-id="a7057-140">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a7057-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="a7057-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="a7057-141">Resumed</span></span>|<span data-ttu-id="a7057-142">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="a7057-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="a7057-143">Started</span><span class="sxs-lookup"><span data-stu-id="a7057-143">Started</span></span>|<span data-ttu-id="a7057-144">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="a7057-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="a7057-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="a7057-145">UnhandledException</span></span>|<span data-ttu-id="a7057-146">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a7057-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="a7057-147">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="a7057-147">Unloaded</span></span>|<span data-ttu-id="a7057-148">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="a7057-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="a7057-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="a7057-149">Canceled</span></span>|<span data-ttu-id="a7057-150">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a7057-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="a7057-151">Angehalten</span><span class="sxs-lookup"><span data-stu-id="a7057-151">Suspended</span></span>|<span data-ttu-id="a7057-152">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="a7057-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="a7057-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="a7057-153">Terminated</span></span>|<span data-ttu-id="a7057-154">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="a7057-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="a7057-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="a7057-155">Unsuspended</span></span>|<span data-ttu-id="a7057-156">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a7057-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7057-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7057-157">Example</span></span>  
 <span data-ttu-id="a7057-158">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="a7057-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7057-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7057-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a7057-160">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a7057-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a7057-161">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a7057-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

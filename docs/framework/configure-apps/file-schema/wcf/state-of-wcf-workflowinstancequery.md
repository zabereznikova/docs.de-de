---
title: '&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 168a6980e955f602ee60bff26461f06cb16c836a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145925"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="00c76-102">&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="00c76-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="00c76-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="00c76-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="00c76-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="00c76-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="00c76-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="00c76-105">\<system.serviceModel></span></span>  
<span data-ttu-id="00c76-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="00c76-106">\<tracking></span></span>  
<span data-ttu-id="00c76-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="00c76-107">\<profiles></span></span>  
<span data-ttu-id="00c76-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="00c76-108">\<trackingProfile></span></span>  
<span data-ttu-id="00c76-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="00c76-109">\<workflow></span></span>  
<span data-ttu-id="00c76-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="00c76-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="00c76-111">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="00c76-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="00c76-112">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00c76-112">\<states></span></span>  
<span data-ttu-id="00c76-113">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00c76-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c76-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="00c76-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00c76-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00c76-115">Attributes and elements</span></span>

<span data-ttu-id="00c76-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00c76-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="00c76-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="00c76-117">Attributes</span></span>

|<span data-ttu-id="00c76-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="00c76-118">Attribute</span></span>|<span data-ttu-id="00c76-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00c76-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="00c76-120">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="00c76-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00c76-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00c76-121">Child elements</span></span>

<span data-ttu-id="00c76-122">Keine</span><span class="sxs-lookup"><span data-stu-id="00c76-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00c76-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00c76-123">Parent elements</span></span>

|<span data-ttu-id="00c76-124">Element</span><span class="sxs-lookup"><span data-stu-id="00c76-124">Element</span></span>|<span data-ttu-id="00c76-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00c76-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00c76-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="00c76-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="00c76-127">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="00c76-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00c76-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00c76-128">Remarks</span></span>  

<span data-ttu-id="00c76-129">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="00c76-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="00c76-130">In der folgenden Tabelle werden die möglichen Statuswerte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="00c76-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="00c76-131">Zustand</span><span class="sxs-lookup"><span data-stu-id="00c76-131">State</span></span>|<span data-ttu-id="00c76-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00c76-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00c76-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="00c76-133">Aborted</span></span>|<span data-ttu-id="00c76-134">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="00c76-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="00c76-135">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="00c76-135">Completed</span></span>|<span data-ttu-id="00c76-136">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="00c76-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="00c76-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="00c76-137">Deleted</span></span>|<span data-ttu-id="00c76-138">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="00c76-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="00c76-139">Idle</span><span class="sxs-lookup"><span data-stu-id="00c76-139">Idle</span></span>|<span data-ttu-id="00c76-140">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="00c76-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="00c76-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="00c76-141">Persisted</span></span>|<span data-ttu-id="00c76-142">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="00c76-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="00c76-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="00c76-143">Resumed</span></span>|<span data-ttu-id="00c76-144">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="00c76-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="00c76-145">Started</span><span class="sxs-lookup"><span data-stu-id="00c76-145">Started</span></span>|<span data-ttu-id="00c76-146">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="00c76-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="00c76-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="00c76-147">UnhandledException</span></span>|<span data-ttu-id="00c76-148">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="00c76-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="00c76-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="00c76-149">Unloaded</span></span>|<span data-ttu-id="00c76-150">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="00c76-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="00c76-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="00c76-151">Canceled</span></span>|<span data-ttu-id="00c76-152">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="00c76-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="00c76-153">Angehalten</span><span class="sxs-lookup"><span data-stu-id="00c76-153">Suspended</span></span>|<span data-ttu-id="00c76-154">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="00c76-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="00c76-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="00c76-155">Terminated</span></span>|<span data-ttu-id="00c76-156">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="00c76-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="00c76-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="00c76-157">Unsuspended</span></span>|<span data-ttu-id="00c76-158">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="00c76-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00c76-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00c76-159">Example</span></span>

<span data-ttu-id="00c76-160">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="00c76-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="00c76-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00c76-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00c76-162">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="00c76-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00c76-163">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="00c76-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

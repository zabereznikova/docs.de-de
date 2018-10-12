---
title: '&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 427cba7a51bfb908171e476cd703c6a40fd6e144
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123214"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="2a329-102">&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="2a329-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="2a329-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="2a329-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2a329-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2a329-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2a329-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a329-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2a329-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="2a329-106">\<tracking></span></span>  
<span data-ttu-id="2a329-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="2a329-107">\<profiles></span></span>  
<span data-ttu-id="2a329-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2a329-108">\<trackingProfile></span></span>  
<span data-ttu-id="2a329-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="2a329-109">\<workflow></span></span>  
<span data-ttu-id="2a329-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="2a329-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="2a329-111">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2a329-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="2a329-112">\<Status ></span><span class="sxs-lookup"><span data-stu-id="2a329-112">\<states></span></span>  
<span data-ttu-id="2a329-113">\<Status ></span><span class="sxs-lookup"><span data-stu-id="2a329-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a329-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a329-114">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a329-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2a329-115">Attributes and elements</span></span>

<span data-ttu-id="2a329-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a329-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2a329-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a329-117">Attributes</span></span>

|<span data-ttu-id="2a329-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="2a329-118">Attribute</span></span>|<span data-ttu-id="2a329-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a329-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2a329-120">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="2a329-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a329-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a329-121">Child elements</span></span>

<span data-ttu-id="2a329-122">Keine</span><span class="sxs-lookup"><span data-stu-id="2a329-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2a329-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a329-123">Parent elements</span></span>

|<span data-ttu-id="2a329-124">Element</span><span class="sxs-lookup"><span data-stu-id="2a329-124">Element</span></span>|<span data-ttu-id="2a329-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a329-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a329-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="2a329-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="2a329-127">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="2a329-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a329-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a329-128">Remarks</span></span>  

<span data-ttu-id="2a329-129">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="2a329-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="2a329-130">In der folgenden Tabelle werden die möglichen Statuswerte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="2a329-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="2a329-131">Zustand</span><span class="sxs-lookup"><span data-stu-id="2a329-131">State</span></span>|<span data-ttu-id="2a329-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a329-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2a329-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="2a329-133">Aborted</span></span>|<span data-ttu-id="2a329-134">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2a329-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2a329-135">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="2a329-135">Completed</span></span>|<span data-ttu-id="2a329-136">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2a329-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2a329-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="2a329-137">Deleted</span></span>|<span data-ttu-id="2a329-138">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2a329-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2a329-139">Idle</span><span class="sxs-lookup"><span data-stu-id="2a329-139">Idle</span></span>|<span data-ttu-id="2a329-140">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="2a329-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2a329-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="2a329-141">Persisted</span></span>|<span data-ttu-id="2a329-142">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2a329-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2a329-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="2a329-143">Resumed</span></span>|<span data-ttu-id="2a329-144">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2a329-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2a329-145">Started</span><span class="sxs-lookup"><span data-stu-id="2a329-145">Started</span></span>|<span data-ttu-id="2a329-146">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="2a329-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2a329-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2a329-147">UnhandledException</span></span>|<span data-ttu-id="2a329-148">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2a329-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2a329-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="2a329-149">Unloaded</span></span>|<span data-ttu-id="2a329-150">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="2a329-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2a329-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="2a329-151">Canceled</span></span>|<span data-ttu-id="2a329-152">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2a329-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2a329-153">Angehalten</span><span class="sxs-lookup"><span data-stu-id="2a329-153">Suspended</span></span>|<span data-ttu-id="2a329-154">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="2a329-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2a329-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="2a329-155">Terminated</span></span>|<span data-ttu-id="2a329-156">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="2a329-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2a329-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="2a329-157">Unsuspended</span></span>|<span data-ttu-id="2a329-158">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2a329-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a329-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a329-159">Example</span></span>

<span data-ttu-id="2a329-160">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="2a329-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml
<workflowInstanceQueries>
  <workflowInstanceQuery>  
    <states>  
      <state name="Started"/>  
    </states>  
  </workflowInstanceQuery>  
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="2a329-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a329-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2a329-162">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2a329-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2a329-163">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2a329-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fd0b57d7d08cf77ba7792e079b7abd2ff8f2839e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947404"
---
# <a name="states"></a><span data-ttu-id="be9a1-101">\<Status ></span><span class="sxs-lookup"><span data-stu-id="be9a1-101">\<states></span></span>
<span data-ttu-id="be9a1-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="be9a1-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="be9a1-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="be9a1-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="be9a1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="be9a1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="be9a1-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="be9a1-105">\<tracking></span></span>  
<span data-ttu-id="be9a1-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="be9a1-106">\<trackingProfile></span></span>  
<span data-ttu-id="be9a1-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="be9a1-107">\<workflow></span></span>  
<span data-ttu-id="be9a1-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="be9a1-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="be9a1-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="be9a1-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="be9a1-110">\<Status ></span><span class="sxs-lookup"><span data-stu-id="be9a1-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be9a1-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="be9a1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be9a1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="be9a1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="be9a1-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be9a1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be9a1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="be9a1-114">Attributes</span></span>  
 <span data-ttu-id="be9a1-115">Keine</span><span class="sxs-lookup"><span data-stu-id="be9a1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be9a1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be9a1-116">Child Elements</span></span>  
  
|<span data-ttu-id="be9a1-117">Element</span><span class="sxs-lookup"><span data-stu-id="be9a1-117">Element</span></span>|<span data-ttu-id="be9a1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be9a1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be9a1-119">\<state></span><span class="sxs-lookup"><span data-stu-id="be9a1-119">\<state></span></span>](states.md)|<span data-ttu-id="be9a1-120">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be9a1-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be9a1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be9a1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="be9a1-122">Element</span><span class="sxs-lookup"><span data-stu-id="be9a1-122">Element</span></span>|<span data-ttu-id="be9a1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be9a1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be9a1-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="be9a1-124">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="be9a1-125">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="be9a1-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be9a1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be9a1-126">Remarks</span></span>  
 <span data-ttu-id="be9a1-127">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="be9a1-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="be9a1-128">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="be9a1-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="be9a1-129">Status</span><span class="sxs-lookup"><span data-stu-id="be9a1-129">State</span></span>|<span data-ttu-id="be9a1-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be9a1-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="be9a1-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="be9a1-131">Aborted</span></span>|<span data-ttu-id="be9a1-132">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="be9a1-133">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="be9a1-133">Completed</span></span>|<span data-ttu-id="be9a1-134">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="be9a1-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="be9a1-135">Deleted</span></span>|<span data-ttu-id="be9a1-136">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="be9a1-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="be9a1-137">Idle</span><span class="sxs-lookup"><span data-stu-id="be9a1-137">Idle</span></span>|<span data-ttu-id="be9a1-138">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="be9a1-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="be9a1-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="be9a1-139">Persisted</span></span>|<span data-ttu-id="be9a1-140">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="be9a1-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="be9a1-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="be9a1-141">Resumed</span></span>|<span data-ttu-id="be9a1-142">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="be9a1-143">Started</span><span class="sxs-lookup"><span data-stu-id="be9a1-143">Started</span></span>|<span data-ttu-id="be9a1-144">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="be9a1-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="be9a1-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="be9a1-145">UnhandledException</span></span>|<span data-ttu-id="be9a1-146">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="be9a1-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="be9a1-147">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="be9a1-147">Unloaded</span></span>|<span data-ttu-id="be9a1-148">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="be9a1-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="be9a1-149">Canceled</span></span>|<span data-ttu-id="be9a1-150">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="be9a1-151">Angehalten</span><span class="sxs-lookup"><span data-stu-id="be9a1-151">Suspended</span></span>|<span data-ttu-id="be9a1-152">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="be9a1-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="be9a1-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="be9a1-153">Terminated</span></span>|<span data-ttu-id="be9a1-154">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="be9a1-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="be9a1-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="be9a1-155">Unsuspended</span></span>|<span data-ttu-id="be9a1-156">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="be9a1-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="be9a1-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be9a1-157">Example</span></span>  
 <span data-ttu-id="be9a1-158">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="be9a1-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be9a1-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be9a1-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="be9a1-160">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="be9a1-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="be9a1-161">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="be9a1-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

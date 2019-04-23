---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108165"
---
# <a name="state"></a><span data-ttu-id="2c450-101">\<state></span><span class="sxs-lookup"><span data-stu-id="2c450-101">\<state></span></span>
<span data-ttu-id="2c450-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="2c450-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2c450-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2c450-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2c450-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2c450-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2c450-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2c450-105">\<tracking></span></span>  
<span data-ttu-id="2c450-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2c450-106">\<trackingProfile></span></span>  
<span data-ttu-id="2c450-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2c450-107">\<workflow></span></span>  
<span data-ttu-id="2c450-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="2c450-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="2c450-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="2c450-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="2c450-110">\<states></span><span class="sxs-lookup"><span data-stu-id="2c450-110">\<states></span></span>  
<span data-ttu-id="2c450-111">\<state></span><span class="sxs-lookup"><span data-stu-id="2c450-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c450-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c450-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c450-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c450-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2c450-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c450-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c450-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c450-115">Attributes</span></span>  
  
|<span data-ttu-id="2c450-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c450-116">Attribute</span></span>|<span data-ttu-id="2c450-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c450-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c450-118">Name</span><span class="sxs-lookup"><span data-stu-id="2c450-118">name</span></span>|<span data-ttu-id="2c450-119">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="2c450-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c450-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c450-120">Child Elements</span></span>  
 <span data-ttu-id="2c450-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2c450-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c450-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c450-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2c450-123">Element</span><span class="sxs-lookup"><span data-stu-id="2c450-123">Element</span></span>|<span data-ttu-id="2c450-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c450-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c450-125">\<states></span><span class="sxs-lookup"><span data-stu-id="2c450-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2c450-126">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="2c450-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c450-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c450-127">Remarks</span></span>  
 <span data-ttu-id="2c450-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="2c450-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="2c450-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2c450-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2c450-130">Zustand</span><span class="sxs-lookup"><span data-stu-id="2c450-130">State</span></span>|<span data-ttu-id="2c450-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c450-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c450-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="2c450-132">Aborted</span></span>|<span data-ttu-id="2c450-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2c450-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2c450-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="2c450-134">Completed</span></span>|<span data-ttu-id="2c450-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2c450-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2c450-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="2c450-136">Deleted</span></span>|<span data-ttu-id="2c450-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2c450-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2c450-138">Idle</span><span class="sxs-lookup"><span data-stu-id="2c450-138">Idle</span></span>|<span data-ttu-id="2c450-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="2c450-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2c450-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="2c450-140">Persisted</span></span>|<span data-ttu-id="2c450-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2c450-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2c450-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="2c450-142">Resumed</span></span>|<span data-ttu-id="2c450-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2c450-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2c450-144">Started</span><span class="sxs-lookup"><span data-stu-id="2c450-144">Started</span></span>|<span data-ttu-id="2c450-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="2c450-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2c450-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2c450-146">UnhandledException</span></span>|<span data-ttu-id="2c450-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2c450-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2c450-148">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="2c450-148">Unloaded</span></span>|<span data-ttu-id="2c450-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="2c450-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2c450-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="2c450-150">Canceled</span></span>|<span data-ttu-id="2c450-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2c450-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2c450-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="2c450-152">Suspended</span></span>|<span data-ttu-id="2c450-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="2c450-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2c450-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="2c450-154">Terminated</span></span>|<span data-ttu-id="2c450-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="2c450-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2c450-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="2c450-156">Unsuspended</span></span>|<span data-ttu-id="2c450-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2c450-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2c450-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c450-158">Example</span></span>  
 <span data-ttu-id="2c450-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="2c450-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c450-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c450-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2c450-161">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2c450-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2c450-162">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2c450-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

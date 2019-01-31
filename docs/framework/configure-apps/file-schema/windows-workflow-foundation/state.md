---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 38b0522b93c051473d7cdc28ae955cc3b7b58efe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287234"
---
# <a name="state"></a><span data-ttu-id="49a64-101">\<state></span><span class="sxs-lookup"><span data-stu-id="49a64-101">\<state></span></span>
<span data-ttu-id="49a64-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="49a64-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="49a64-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="49a64-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="49a64-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49a64-104">\<system.serviceModel></span></span>  
<span data-ttu-id="49a64-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="49a64-105">\<tracking></span></span>  
<span data-ttu-id="49a64-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="49a64-106">\<trackingProfile></span></span>  
<span data-ttu-id="49a64-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="49a64-107">\<workflow></span></span>  
<span data-ttu-id="49a64-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="49a64-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="49a64-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="49a64-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="49a64-110">\<states></span><span class="sxs-lookup"><span data-stu-id="49a64-110">\<states></span></span>  
<span data-ttu-id="49a64-111">\<state></span><span class="sxs-lookup"><span data-stu-id="49a64-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a64-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="49a64-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49a64-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="49a64-113">Attributes and Elements</span></span>  
 <span data-ttu-id="49a64-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49a64-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49a64-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="49a64-115">Attributes</span></span>  
  
|<span data-ttu-id="49a64-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="49a64-116">Attribute</span></span>|<span data-ttu-id="49a64-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49a64-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49a64-118">Name</span><span class="sxs-lookup"><span data-stu-id="49a64-118">name</span></span>|<span data-ttu-id="49a64-119">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="49a64-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49a64-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49a64-120">Child Elements</span></span>  
 <span data-ttu-id="49a64-121">Keine</span><span class="sxs-lookup"><span data-stu-id="49a64-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49a64-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49a64-122">Parent Elements</span></span>  
  
|<span data-ttu-id="49a64-123">Element</span><span class="sxs-lookup"><span data-stu-id="49a64-123">Element</span></span>|<span data-ttu-id="49a64-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49a64-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49a64-125">\<states></span><span class="sxs-lookup"><span data-stu-id="49a64-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="49a64-126">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="49a64-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49a64-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49a64-127">Remarks</span></span>  
 <span data-ttu-id="49a64-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="49a64-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="49a64-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="49a64-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="49a64-130">Zustand</span><span class="sxs-lookup"><span data-stu-id="49a64-130">State</span></span>|<span data-ttu-id="49a64-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49a64-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="49a64-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="49a64-132">Aborted</span></span>|<span data-ttu-id="49a64-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="49a64-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="49a64-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="49a64-134">Completed</span></span>|<span data-ttu-id="49a64-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="49a64-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="49a64-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="49a64-136">Deleted</span></span>|<span data-ttu-id="49a64-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="49a64-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="49a64-138">Idle</span><span class="sxs-lookup"><span data-stu-id="49a64-138">Idle</span></span>|<span data-ttu-id="49a64-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="49a64-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="49a64-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="49a64-140">Persisted</span></span>|<span data-ttu-id="49a64-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="49a64-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="49a64-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="49a64-142">Resumed</span></span>|<span data-ttu-id="49a64-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="49a64-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="49a64-144">Started</span><span class="sxs-lookup"><span data-stu-id="49a64-144">Started</span></span>|<span data-ttu-id="49a64-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="49a64-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="49a64-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="49a64-146">UnhandledException</span></span>|<span data-ttu-id="49a64-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="49a64-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="49a64-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="49a64-148">Unloaded</span></span>|<span data-ttu-id="49a64-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="49a64-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="49a64-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="49a64-150">Canceled</span></span>|<span data-ttu-id="49a64-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="49a64-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="49a64-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="49a64-152">Suspended</span></span>|<span data-ttu-id="49a64-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="49a64-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="49a64-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="49a64-154">Terminated</span></span>|<span data-ttu-id="49a64-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="49a64-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="49a64-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="49a64-156">Unsuspended</span></span>|<span data-ttu-id="49a64-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="49a64-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49a64-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49a64-158">Example</span></span>  
 <span data-ttu-id="49a64-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="49a64-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49a64-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49a64-160">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="49a64-161">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="49a64-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="49a64-162">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="49a64-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

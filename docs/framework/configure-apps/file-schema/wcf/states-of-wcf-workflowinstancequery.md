---
title: <states>von WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855039"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="af134-102">\<Zustände > von WCF, \<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="af134-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="af134-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="af134-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="af134-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="af134-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="af134-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af134-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af134-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="af134-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="af134-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af134-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="af134-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="af134-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="af134-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af134-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="af134-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af134-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="af134-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowinstancequeries->** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af134-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="af134-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WorkflowInstanceQuery->** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af134-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="af134-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Status >**</span><span class="sxs-lookup"><span data-stu-id="af134-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af134-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="af134-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af134-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af134-115">Attributes and elements</span></span>

<span data-ttu-id="af134-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af134-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af134-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="af134-117">Attributes</span></span>  

<span data-ttu-id="af134-118">Keine</span><span class="sxs-lookup"><span data-stu-id="af134-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af134-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af134-119">Child elements</span></span>
  
|<span data-ttu-id="af134-120">Element</span><span class="sxs-lookup"><span data-stu-id="af134-120">Element</span></span>|<span data-ttu-id="af134-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af134-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af134-122">\<Status ></span><span class="sxs-lookup"><span data-stu-id="af134-122">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="af134-123">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="af134-123">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af134-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af134-124">Parent elements</span></span>  
  
|<span data-ttu-id="af134-125">Element</span><span class="sxs-lookup"><span data-stu-id="af134-125">Element</span></span>|<span data-ttu-id="af134-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af134-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af134-127">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="af134-127">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="af134-128">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="af134-128">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af134-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af134-129">Remarks</span></span>

<span data-ttu-id="af134-130">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="af134-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="af134-131">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="af134-131">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="af134-132">Status</span><span class="sxs-lookup"><span data-stu-id="af134-132">State</span></span>|<span data-ttu-id="af134-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af134-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af134-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="af134-134">Aborted</span></span>|<span data-ttu-id="af134-135">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="af134-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="af134-136">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="af134-136">Completed</span></span>|<span data-ttu-id="af134-137">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="af134-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="af134-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="af134-138">Deleted</span></span>|<span data-ttu-id="af134-139">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="af134-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="af134-140">Idle</span><span class="sxs-lookup"><span data-stu-id="af134-140">Idle</span></span>|<span data-ttu-id="af134-141">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="af134-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="af134-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="af134-142">Persisted</span></span>|<span data-ttu-id="af134-143">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="af134-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="af134-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="af134-144">Resumed</span></span>|<span data-ttu-id="af134-145">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="af134-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="af134-146">Started</span><span class="sxs-lookup"><span data-stu-id="af134-146">Started</span></span>|<span data-ttu-id="af134-147">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="af134-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="af134-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="af134-148">UnhandledException</span></span>|<span data-ttu-id="af134-149">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="af134-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="af134-150">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="af134-150">Unloaded</span></span>|<span data-ttu-id="af134-151">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="af134-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="af134-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="af134-152">Canceled</span></span>|<span data-ttu-id="af134-153">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="af134-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="af134-154">Angehalten</span><span class="sxs-lookup"><span data-stu-id="af134-154">Suspended</span></span>|<span data-ttu-id="af134-155">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="af134-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="af134-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="af134-156">Terminated</span></span>|<span data-ttu-id="af134-157">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="af134-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="af134-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="af134-158">Unsuspended</span></span>|<span data-ttu-id="af134-159">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="af134-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="af134-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af134-160">Example</span></span>

<span data-ttu-id="af134-161">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="af134-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="af134-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af134-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="af134-163">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="af134-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="af134-164">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="af134-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

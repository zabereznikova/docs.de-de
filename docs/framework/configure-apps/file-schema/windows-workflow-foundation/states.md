---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398619"
---
# <a name="states"></a><span data-ttu-id="466f4-101">\<Status ></span><span class="sxs-lookup"><span data-stu-id="466f4-101">\<states></span></span>
<span data-ttu-id="466f4-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="466f4-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="466f4-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="466f4-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="466f4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="466f4-105">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="466f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="466f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="466f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="466f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowinstancequeries->** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="466f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WorkflowInstanceQuery->** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="466f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="466f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Status >**</span><span class="sxs-lookup"><span data-stu-id="466f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466f4-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="466f4-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="466f4-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="466f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="466f4-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="466f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="466f4-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="466f4-115">Attributes</span></span>  
 <span data-ttu-id="466f4-116">Keine</span><span class="sxs-lookup"><span data-stu-id="466f4-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="466f4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="466f4-117">Child Elements</span></span>  
  
|<span data-ttu-id="466f4-118">Element</span><span class="sxs-lookup"><span data-stu-id="466f4-118">Element</span></span>|<span data-ttu-id="466f4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466f4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="466f4-120">\<state></span><span class="sxs-lookup"><span data-stu-id="466f4-120">\<state></span></span>](states.md)|<span data-ttu-id="466f4-121">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="466f4-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="466f4-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="466f4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="466f4-123">Element</span><span class="sxs-lookup"><span data-stu-id="466f4-123">Element</span></span>|<span data-ttu-id="466f4-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466f4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="466f4-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="466f4-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="466f4-126">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="466f4-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466f4-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="466f4-127">Remarks</span></span>  
 <span data-ttu-id="466f4-128">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="466f4-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="466f4-129">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="466f4-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="466f4-130">Status</span><span class="sxs-lookup"><span data-stu-id="466f4-130">State</span></span>|<span data-ttu-id="466f4-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466f4-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="466f4-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="466f4-132">Aborted</span></span>|<span data-ttu-id="466f4-133">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="466f4-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="466f4-134">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="466f4-134">Completed</span></span>|<span data-ttu-id="466f4-135">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="466f4-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="466f4-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="466f4-136">Deleted</span></span>|<span data-ttu-id="466f4-137">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="466f4-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="466f4-138">Idle</span><span class="sxs-lookup"><span data-stu-id="466f4-138">Idle</span></span>|<span data-ttu-id="466f4-139">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="466f4-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="466f4-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="466f4-140">Persisted</span></span>|<span data-ttu-id="466f4-141">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="466f4-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="466f4-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="466f4-142">Resumed</span></span>|<span data-ttu-id="466f4-143">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="466f4-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="466f4-144">Started</span><span class="sxs-lookup"><span data-stu-id="466f4-144">Started</span></span>|<span data-ttu-id="466f4-145">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="466f4-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="466f4-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="466f4-146">UnhandledException</span></span>|<span data-ttu-id="466f4-147">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="466f4-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="466f4-148">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="466f4-148">Unloaded</span></span>|<span data-ttu-id="466f4-149">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="466f4-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="466f4-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="466f4-150">Canceled</span></span>|<span data-ttu-id="466f4-151">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="466f4-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="466f4-152">Angehalten</span><span class="sxs-lookup"><span data-stu-id="466f4-152">Suspended</span></span>|<span data-ttu-id="466f4-153">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="466f4-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="466f4-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="466f4-154">Terminated</span></span>|<span data-ttu-id="466f4-155">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="466f4-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="466f4-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="466f4-156">Unsuspended</span></span>|<span data-ttu-id="466f4-157">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="466f4-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="466f4-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="466f4-158">Example</span></span>  
 <span data-ttu-id="466f4-159">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="466f4-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="466f4-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="466f4-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="466f4-161">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="466f4-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="466f4-162">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="466f4-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

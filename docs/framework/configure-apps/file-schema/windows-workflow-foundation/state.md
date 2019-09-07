---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398638"
---
# <a name="state"></a><span data-ttu-id="4a394-101">\<Status ></span><span class="sxs-lookup"><span data-stu-id="4a394-101">\<state></span></span>
<span data-ttu-id="4a394-102">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="4a394-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="4a394-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4a394-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4a394-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a394-105">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4a394-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="4a394-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="4a394-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="4a394-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowinstancequeries->** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="4a394-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WorkflowInstanceQuery->** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="4a394-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Status >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="4a394-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="4a394-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Status >**</span><span class="sxs-lookup"><span data-stu-id="4a394-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a394-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a394-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a394-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4a394-114">Attributes and Elements</span></span>  
 <span data-ttu-id="4a394-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a394-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a394-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="4a394-116">Attributes</span></span>  
  
|<span data-ttu-id="4a394-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="4a394-117">Attribute</span></span>|<span data-ttu-id="4a394-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a394-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a394-119">Name</span><span class="sxs-lookup"><span data-stu-id="4a394-119">name</span></span>|<span data-ttu-id="4a394-120">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="4a394-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a394-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a394-121">Child Elements</span></span>  
 <span data-ttu-id="4a394-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4a394-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a394-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a394-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4a394-124">Element</span><span class="sxs-lookup"><span data-stu-id="4a394-124">Element</span></span>|<span data-ttu-id="4a394-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a394-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a394-126">\<Status ></span><span class="sxs-lookup"><span data-stu-id="4a394-126">\<states></span></span>](states.md)|<span data-ttu-id="4a394-127">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="4a394-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a394-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a394-128">Remarks</span></span>  
 <span data-ttu-id="4a394-129">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="4a394-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="4a394-130">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4a394-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="4a394-131">Status</span><span class="sxs-lookup"><span data-stu-id="4a394-131">State</span></span>|<span data-ttu-id="4a394-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a394-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4a394-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="4a394-133">Aborted</span></span>|<span data-ttu-id="4a394-134">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4a394-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="4a394-135">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="4a394-135">Completed</span></span>|<span data-ttu-id="4a394-136">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4a394-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="4a394-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="4a394-137">Deleted</span></span>|<span data-ttu-id="4a394-138">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4a394-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="4a394-139">Idle</span><span class="sxs-lookup"><span data-stu-id="4a394-139">Idle</span></span>|<span data-ttu-id="4a394-140">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="4a394-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="4a394-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="4a394-141">Persisted</span></span>|<span data-ttu-id="4a394-142">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4a394-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="4a394-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="4a394-143">Resumed</span></span>|<span data-ttu-id="4a394-144">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="4a394-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="4a394-145">Started</span><span class="sxs-lookup"><span data-stu-id="4a394-145">Started</span></span>|<span data-ttu-id="4a394-146">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="4a394-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="4a394-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="4a394-147">UnhandledException</span></span>|<span data-ttu-id="4a394-148">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4a394-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="4a394-149">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="4a394-149">Unloaded</span></span>|<span data-ttu-id="4a394-150">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="4a394-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="4a394-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="4a394-151">Canceled</span></span>|<span data-ttu-id="4a394-152">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4a394-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="4a394-153">Angehalten</span><span class="sxs-lookup"><span data-stu-id="4a394-153">Suspended</span></span>|<span data-ttu-id="4a394-154">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="4a394-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="4a394-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="4a394-155">Terminated</span></span>|<span data-ttu-id="4a394-156">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="4a394-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="4a394-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="4a394-157">Unsuspended</span></span>|<span data-ttu-id="4a394-158">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4a394-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4a394-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a394-159">Example</span></span>  
 <span data-ttu-id="4a394-160">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="4a394-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a394-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a394-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4a394-162">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="4a394-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4a394-163">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="4a394-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

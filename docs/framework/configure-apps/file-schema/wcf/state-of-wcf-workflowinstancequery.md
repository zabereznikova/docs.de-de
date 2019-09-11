---
title: <state>von WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854951"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="326ab-102">\<Status > von WCF, \<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="326ab-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="326ab-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="326ab-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="326ab-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="326ab-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="326ab-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="326ab-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="326ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="326ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="326ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="326ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="326ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="326ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowinstancequeries->** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="326ab-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WorkflowInstanceQuery->** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="326ab-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Status >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="326ab-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="326ab-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Status >**</span><span class="sxs-lookup"><span data-stu-id="326ab-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326ab-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="326ab-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="326ab-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="326ab-116">Attributes and elements</span></span>

<span data-ttu-id="326ab-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="326ab-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="326ab-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="326ab-118">Attributes</span></span>

|<span data-ttu-id="326ab-119">Attribut</span><span class="sxs-lookup"><span data-stu-id="326ab-119">Attribute</span></span>|<span data-ttu-id="326ab-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="326ab-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="326ab-121">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="326ab-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="326ab-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="326ab-122">Child elements</span></span>

<span data-ttu-id="326ab-123">Keine</span><span class="sxs-lookup"><span data-stu-id="326ab-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="326ab-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="326ab-124">Parent elements</span></span>

|<span data-ttu-id="326ab-125">Element</span><span class="sxs-lookup"><span data-stu-id="326ab-125">Element</span></span>|<span data-ttu-id="326ab-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="326ab-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="326ab-127">\<Status ></span><span class="sxs-lookup"><span data-stu-id="326ab-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="326ab-128">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="326ab-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="326ab-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="326ab-129">Remarks</span></span>  

<span data-ttu-id="326ab-130">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="326ab-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="326ab-131">Mögliche Zustands Werte werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="326ab-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="326ab-132">Status</span><span class="sxs-lookup"><span data-stu-id="326ab-132">State</span></span>|<span data-ttu-id="326ab-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="326ab-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="326ab-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="326ab-134">Aborted</span></span>|<span data-ttu-id="326ab-135">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="326ab-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="326ab-136">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="326ab-136">Completed</span></span>|<span data-ttu-id="326ab-137">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="326ab-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="326ab-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="326ab-138">Deleted</span></span>|<span data-ttu-id="326ab-139">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="326ab-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="326ab-140">Idle</span><span class="sxs-lookup"><span data-stu-id="326ab-140">Idle</span></span>|<span data-ttu-id="326ab-141">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="326ab-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="326ab-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="326ab-142">Persisted</span></span>|<span data-ttu-id="326ab-143">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="326ab-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="326ab-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="326ab-144">Resumed</span></span>|<span data-ttu-id="326ab-145">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="326ab-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="326ab-146">Started</span><span class="sxs-lookup"><span data-stu-id="326ab-146">Started</span></span>|<span data-ttu-id="326ab-147">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="326ab-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="326ab-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="326ab-148">UnhandledException</span></span>|<span data-ttu-id="326ab-149">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="326ab-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="326ab-150">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="326ab-150">Unloaded</span></span>|<span data-ttu-id="326ab-151">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="326ab-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="326ab-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="326ab-152">Canceled</span></span>|<span data-ttu-id="326ab-153">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="326ab-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="326ab-154">Angehalten</span><span class="sxs-lookup"><span data-stu-id="326ab-154">Suspended</span></span>|<span data-ttu-id="326ab-155">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="326ab-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="326ab-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="326ab-156">Terminated</span></span>|<span data-ttu-id="326ab-157">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="326ab-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="326ab-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="326ab-158">Unsuspended</span></span>|<span data-ttu-id="326ab-159">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="326ab-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="326ab-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="326ab-160">Example</span></span>

<span data-ttu-id="326ab-161">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="326ab-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="326ab-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="326ab-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="326ab-163">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="326ab-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="326ab-164">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="326ab-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

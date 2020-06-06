---
title: <states>von WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855039"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="fc5ea-102">\<states>von WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="fc5ea-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="fc5ea-103">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="fc5ea-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="fc5ea-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="fc5ea-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc5ea-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc5ea-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc5ea-106">Attributes and elements</span></span>

<span data-ttu-id="fc5ea-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc5ea-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc5ea-108">Attributes</span></span>  

<span data-ttu-id="fc5ea-109">Keine</span><span class="sxs-lookup"><span data-stu-id="fc5ea-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc5ea-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc5ea-110">Child elements</span></span>
  
|<span data-ttu-id="fc5ea-111">Element</span><span class="sxs-lookup"><span data-stu-id="fc5ea-111">Element</span></span>|<span data-ttu-id="fc5ea-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fc5ea-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="fc5ea-113">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-113">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc5ea-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc5ea-114">Parent elements</span></span>  
  
|<span data-ttu-id="fc5ea-115">Element</span><span class="sxs-lookup"><span data-stu-id="fc5ea-115">Element</span></span>|<span data-ttu-id="fc5ea-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fc5ea-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="fc5ea-117">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-117">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc5ea-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc5ea-118">Remarks</span></span>

<span data-ttu-id="fc5ea-119">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="fc5ea-120">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="fc5ea-121">Staat</span><span class="sxs-lookup"><span data-stu-id="fc5ea-121">State</span></span>|<span data-ttu-id="fc5ea-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fc5ea-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc5ea-123">Aborted</span><span class="sxs-lookup"><span data-stu-id="fc5ea-123">Aborted</span></span>|<span data-ttu-id="fc5ea-124">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="fc5ea-125">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="fc5ea-125">Completed</span></span>|<span data-ttu-id="fc5ea-126">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="fc5ea-127">Gelöscht</span><span class="sxs-lookup"><span data-stu-id="fc5ea-127">Deleted</span></span>|<span data-ttu-id="fc5ea-128">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="fc5ea-129">Idle</span><span class="sxs-lookup"><span data-stu-id="fc5ea-129">Idle</span></span>|<span data-ttu-id="fc5ea-130">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="fc5ea-131">Persisted</span><span class="sxs-lookup"><span data-stu-id="fc5ea-131">Persisted</span></span>|<span data-ttu-id="fc5ea-132">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="fc5ea-133">Resumed</span><span class="sxs-lookup"><span data-stu-id="fc5ea-133">Resumed</span></span>|<span data-ttu-id="fc5ea-134">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="fc5ea-135">Started</span><span class="sxs-lookup"><span data-stu-id="fc5ea-135">Started</span></span>|<span data-ttu-id="fc5ea-136">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="fc5ea-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="fc5ea-137">UnhandledException</span></span>|<span data-ttu-id="fc5ea-138">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="fc5ea-139">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="fc5ea-139">Unloaded</span></span>|<span data-ttu-id="fc5ea-140">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="fc5ea-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="fc5ea-141">Canceled</span></span>|<span data-ttu-id="fc5ea-142">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="fc5ea-143">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="fc5ea-143">Suspended</span></span>|<span data-ttu-id="fc5ea-144">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="fc5ea-145">Terminated</span><span class="sxs-lookup"><span data-stu-id="fc5ea-145">Terminated</span></span>|<span data-ttu-id="fc5ea-146">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="fc5ea-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="fc5ea-147">Unsuspended</span></span>|<span data-ttu-id="fc5ea-148">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc5ea-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc5ea-149">Example</span></span>

<span data-ttu-id="fc5ea-150">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc5ea-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc5ea-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fc5ea-152">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="fc5ea-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fc5ea-153">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="fc5ea-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

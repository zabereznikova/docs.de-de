---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398619"
---
# \<states>
<span data-ttu-id="5f878-101">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="5f878-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="5f878-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="5f878-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="5f878-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f878-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f878-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5f878-104">Attributes and Elements</span></span>  
 <span data-ttu-id="5f878-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5f878-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f878-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="5f878-106">Attributes</span></span>  
 <span data-ttu-id="5f878-107">Keine</span><span class="sxs-lookup"><span data-stu-id="5f878-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f878-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5f878-108">Child Elements</span></span>  
  
|<span data-ttu-id="5f878-109">Element</span><span class="sxs-lookup"><span data-stu-id="5f878-109">Element</span></span>|<span data-ttu-id="5f878-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5f878-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="5f878-111">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f878-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f878-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5f878-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5f878-113">Element</span><span class="sxs-lookup"><span data-stu-id="5f878-113">Element</span></span>|<span data-ttu-id="5f878-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5f878-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="5f878-115">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5f878-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f878-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5f878-116">Remarks</span></span>  
 <span data-ttu-id="5f878-117">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="5f878-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="5f878-118">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5f878-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="5f878-119">Staat</span><span class="sxs-lookup"><span data-stu-id="5f878-119">State</span></span>|<span data-ttu-id="5f878-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5f878-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f878-121">Aborted</span><span class="sxs-lookup"><span data-stu-id="5f878-121">Aborted</span></span>|<span data-ttu-id="5f878-122">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5f878-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="5f878-123">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5f878-123">Completed</span></span>|<span data-ttu-id="5f878-124">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5f878-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="5f878-125">Gelöscht</span><span class="sxs-lookup"><span data-stu-id="5f878-125">Deleted</span></span>|<span data-ttu-id="5f878-126">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5f878-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="5f878-127">Idle</span><span class="sxs-lookup"><span data-stu-id="5f878-127">Idle</span></span>|<span data-ttu-id="5f878-128">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="5f878-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="5f878-129">Persisted</span><span class="sxs-lookup"><span data-stu-id="5f878-129">Persisted</span></span>|<span data-ttu-id="5f878-130">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5f878-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="5f878-131">Resumed</span><span class="sxs-lookup"><span data-stu-id="5f878-131">Resumed</span></span>|<span data-ttu-id="5f878-132">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="5f878-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="5f878-133">Started</span><span class="sxs-lookup"><span data-stu-id="5f878-133">Started</span></span>|<span data-ttu-id="5f878-134">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="5f878-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="5f878-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="5f878-135">UnhandledException</span></span>|<span data-ttu-id="5f878-136">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5f878-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="5f878-137">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="5f878-137">Unloaded</span></span>|<span data-ttu-id="5f878-138">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="5f878-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="5f878-139">Canceled</span><span class="sxs-lookup"><span data-stu-id="5f878-139">Canceled</span></span>|<span data-ttu-id="5f878-140">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5f878-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="5f878-141">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="5f878-141">Suspended</span></span>|<span data-ttu-id="5f878-142">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="5f878-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="5f878-143">Terminated</span><span class="sxs-lookup"><span data-stu-id="5f878-143">Terminated</span></span>|<span data-ttu-id="5f878-144">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="5f878-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="5f878-145">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="5f878-145">Unsuspended</span></span>|<span data-ttu-id="5f878-146">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5f878-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f878-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f878-147">Example</span></span>  
 <span data-ttu-id="5f878-148">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="5f878-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f878-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f878-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5f878-150">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="5f878-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5f878-151">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="5f878-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

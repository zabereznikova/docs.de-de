---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: e759f86e7746eaf3fdd72ed923612b24ef9b0c23
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150816"
---
# \<states>

<span data-ttu-id="2838f-101">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="2838f-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2838f-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="2838f-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="2838f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="2838f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2838f-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2838f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2838f-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2838f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2838f-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="2838f-106">Attributes</span></span>  

 <span data-ttu-id="2838f-107">Keine</span><span class="sxs-lookup"><span data-stu-id="2838f-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2838f-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2838f-108">Child Elements</span></span>  
  
|<span data-ttu-id="2838f-109">Element</span><span class="sxs-lookup"><span data-stu-id="2838f-109">Element</span></span>|<span data-ttu-id="2838f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2838f-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="2838f-111">Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2838f-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2838f-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2838f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2838f-113">Element</span><span class="sxs-lookup"><span data-stu-id="2838f-113">Element</span></span>|<span data-ttu-id="2838f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2838f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="2838f-115">Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2838f-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2838f-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2838f-116">Remarks</span></span>  

 <span data-ttu-id="2838f-117">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="2838f-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="2838f-118">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2838f-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2838f-119">State</span><span class="sxs-lookup"><span data-stu-id="2838f-119">State</span></span>|<span data-ttu-id="2838f-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2838f-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2838f-121">Aborted</span><span class="sxs-lookup"><span data-stu-id="2838f-121">Aborted</span></span>|<span data-ttu-id="2838f-122">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2838f-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2838f-123">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="2838f-123">Completed</span></span>|<span data-ttu-id="2838f-124">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2838f-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2838f-125">Deleted</span><span class="sxs-lookup"><span data-stu-id="2838f-125">Deleted</span></span>|<span data-ttu-id="2838f-126">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2838f-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2838f-127">Idle</span><span class="sxs-lookup"><span data-stu-id="2838f-127">Idle</span></span>|<span data-ttu-id="2838f-128">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="2838f-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2838f-129">Persistent</span><span class="sxs-lookup"><span data-stu-id="2838f-129">Persisted</span></span>|<span data-ttu-id="2838f-130">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2838f-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2838f-131">Resumed</span><span class="sxs-lookup"><span data-stu-id="2838f-131">Resumed</span></span>|<span data-ttu-id="2838f-132">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2838f-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2838f-133">Gestartet</span><span class="sxs-lookup"><span data-stu-id="2838f-133">Started</span></span>|<span data-ttu-id="2838f-134">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="2838f-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2838f-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2838f-135">UnhandledException</span></span>|<span data-ttu-id="2838f-136">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2838f-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2838f-137">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="2838f-137">Unloaded</span></span>|<span data-ttu-id="2838f-138">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="2838f-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2838f-139">Canceled</span><span class="sxs-lookup"><span data-stu-id="2838f-139">Canceled</span></span>|<span data-ttu-id="2838f-140">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2838f-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2838f-141">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="2838f-141">Suspended</span></span>|<span data-ttu-id="2838f-142">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="2838f-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2838f-143">Beendet</span><span class="sxs-lookup"><span data-stu-id="2838f-143">Terminated</span></span>|<span data-ttu-id="2838f-144">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="2838f-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2838f-145">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="2838f-145">Unsuspended</span></span>|<span data-ttu-id="2838f-146">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2838f-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2838f-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2838f-147">Example</span></span>  

 <span data-ttu-id="2838f-148">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="2838f-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2838f-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2838f-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2838f-150">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2838f-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2838f-151">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2838f-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

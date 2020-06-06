---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398638"
---
# \<state>
<span data-ttu-id="53b56-101">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="53b56-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="53b56-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="53b56-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="53b56-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="53b56-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b56-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53b56-104">Attributes and Elements</span></span>  
 <span data-ttu-id="53b56-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53b56-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b56-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="53b56-106">Attributes</span></span>  
  
|<span data-ttu-id="53b56-107">attribute</span><span class="sxs-lookup"><span data-stu-id="53b56-107">Attribute</span></span>|<span data-ttu-id="53b56-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53b56-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53b56-109">name</span><span class="sxs-lookup"><span data-stu-id="53b56-109">name</span></span>|<span data-ttu-id="53b56-110">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="53b56-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53b56-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53b56-111">Child Elements</span></span>  
 <span data-ttu-id="53b56-112">Keine</span><span class="sxs-lookup"><span data-stu-id="53b56-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53b56-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53b56-113">Parent Elements</span></span>  
  
|<span data-ttu-id="53b56-114">Element</span><span class="sxs-lookup"><span data-stu-id="53b56-114">Element</span></span>|<span data-ttu-id="53b56-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53b56-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="53b56-116">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="53b56-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b56-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="53b56-117">Remarks</span></span>  
 <span data-ttu-id="53b56-118">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="53b56-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="53b56-119">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="53b56-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="53b56-120">Staat</span><span class="sxs-lookup"><span data-stu-id="53b56-120">State</span></span>|<span data-ttu-id="53b56-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53b56-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53b56-122">Aborted</span><span class="sxs-lookup"><span data-stu-id="53b56-122">Aborted</span></span>|<span data-ttu-id="53b56-123">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="53b56-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="53b56-124">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="53b56-124">Completed</span></span>|<span data-ttu-id="53b56-125">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="53b56-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="53b56-126">Gelöscht</span><span class="sxs-lookup"><span data-stu-id="53b56-126">Deleted</span></span>|<span data-ttu-id="53b56-127">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="53b56-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="53b56-128">Idle</span><span class="sxs-lookup"><span data-stu-id="53b56-128">Idle</span></span>|<span data-ttu-id="53b56-129">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="53b56-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="53b56-130">Persisted</span><span class="sxs-lookup"><span data-stu-id="53b56-130">Persisted</span></span>|<span data-ttu-id="53b56-131">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="53b56-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="53b56-132">Resumed</span><span class="sxs-lookup"><span data-stu-id="53b56-132">Resumed</span></span>|<span data-ttu-id="53b56-133">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="53b56-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="53b56-134">Started</span><span class="sxs-lookup"><span data-stu-id="53b56-134">Started</span></span>|<span data-ttu-id="53b56-135">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="53b56-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="53b56-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="53b56-136">UnhandledException</span></span>|<span data-ttu-id="53b56-137">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="53b56-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="53b56-138">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="53b56-138">Unloaded</span></span>|<span data-ttu-id="53b56-139">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="53b56-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="53b56-140">Canceled</span><span class="sxs-lookup"><span data-stu-id="53b56-140">Canceled</span></span>|<span data-ttu-id="53b56-141">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="53b56-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="53b56-142">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="53b56-142">Suspended</span></span>|<span data-ttu-id="53b56-143">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="53b56-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="53b56-144">Terminated</span><span class="sxs-lookup"><span data-stu-id="53b56-144">Terminated</span></span>|<span data-ttu-id="53b56-145">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="53b56-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="53b56-146">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="53b56-146">Unsuspended</span></span>|<span data-ttu-id="53b56-147">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="53b56-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53b56-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53b56-148">Example</span></span>  
 <span data-ttu-id="53b56-149">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="53b56-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b56-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53b56-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="53b56-151">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="53b56-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="53b56-152">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="53b56-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

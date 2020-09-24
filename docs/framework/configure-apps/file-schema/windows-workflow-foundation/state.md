---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 169fa900b5be9a9577818b68b540184afd4a6681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169725"
---
# \<state>

<span data-ttu-id="0a37d-101">Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="0a37d-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="0a37d-102">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0a37d-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="0a37d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a37d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a37d-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a37d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0a37d-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a37d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a37d-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a37d-106">Attributes</span></span>  
  
|<span data-ttu-id="0a37d-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0a37d-107">Attribute</span></span>|<span data-ttu-id="0a37d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a37d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a37d-109">name</span><span class="sxs-lookup"><span data-stu-id="0a37d-109">name</span></span>|<span data-ttu-id="0a37d-110">Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="0a37d-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a37d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a37d-111">Child Elements</span></span>  

 <span data-ttu-id="0a37d-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0a37d-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a37d-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a37d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0a37d-114">Element</span><span class="sxs-lookup"><span data-stu-id="0a37d-114">Element</span></span>|<span data-ttu-id="0a37d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a37d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="0a37d-116">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a37d-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0a37d-117">Remarks</span></span>  

 <span data-ttu-id="0a37d-118">Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.</span><span class="sxs-lookup"><span data-stu-id="0a37d-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="0a37d-119">Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0a37d-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="0a37d-120">State</span><span class="sxs-lookup"><span data-stu-id="0a37d-120">State</span></span>|<span data-ttu-id="0a37d-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a37d-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0a37d-122">Aborted</span><span class="sxs-lookup"><span data-stu-id="0a37d-122">Aborted</span></span>|<span data-ttu-id="0a37d-123">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="0a37d-124">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="0a37d-124">Completed</span></span>|<span data-ttu-id="0a37d-125">Die Workflowinstanz wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="0a37d-126">Deleted</span><span class="sxs-lookup"><span data-stu-id="0a37d-126">Deleted</span></span>|<span data-ttu-id="0a37d-127">Die Workflowinstanz wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0a37d-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="0a37d-128">Idle</span><span class="sxs-lookup"><span data-stu-id="0a37d-128">Idle</span></span>|<span data-ttu-id="0a37d-129">Die Workflowinstanz ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="0a37d-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="0a37d-130">Persistent</span><span class="sxs-lookup"><span data-stu-id="0a37d-130">Persisted</span></span>|<span data-ttu-id="0a37d-131">Die Workflowinstanz wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0a37d-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="0a37d-132">Resumed</span><span class="sxs-lookup"><span data-stu-id="0a37d-132">Resumed</span></span>|<span data-ttu-id="0a37d-133">Die Workflowinstanz wurde wiederaufgenommen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="0a37d-134">Gestartet</span><span class="sxs-lookup"><span data-stu-id="0a37d-134">Started</span></span>|<span data-ttu-id="0a37d-135">Die Workflowinstanz wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="0a37d-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="0a37d-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="0a37d-136">UnhandledException</span></span>|<span data-ttu-id="0a37d-137">In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0a37d-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="0a37d-138">Nicht Geladen</span><span class="sxs-lookup"><span data-stu-id="0a37d-138">Unloaded</span></span>|<span data-ttu-id="0a37d-139">Die Workflowinstanz wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="0a37d-140">Canceled</span><span class="sxs-lookup"><span data-stu-id="0a37d-140">Canceled</span></span>|<span data-ttu-id="0a37d-141">Die Workflowinstanz wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="0a37d-142">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="0a37d-142">Suspended</span></span>|<span data-ttu-id="0a37d-143">Die Workflowinstanz wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="0a37d-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="0a37d-144">Beendet</span><span class="sxs-lookup"><span data-stu-id="0a37d-144">Terminated</span></span>|<span data-ttu-id="0a37d-145">Die Workflowinstanz wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="0a37d-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="0a37d-146">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="0a37d-146">Unsuspended</span></span>|<span data-ttu-id="0a37d-147">Die Workflowinstanz wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0a37d-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0a37d-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a37d-148">Example</span></span>  

 <span data-ttu-id="0a37d-149">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="0a37d-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a37d-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a37d-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0a37d-151">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0a37d-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0a37d-152">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0a37d-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

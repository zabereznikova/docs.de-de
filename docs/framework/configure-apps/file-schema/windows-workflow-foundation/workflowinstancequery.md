---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 6fe02cfea91633da41c8ebc7d8a78dd005ad3f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080903"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="a3f34-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a3f34-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="a3f34-102">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a3f34-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="a3f34-103">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a3f34-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a3f34-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3f34-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a3f34-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a3f34-105">\<tracking></span></span>  
<span data-ttu-id="a3f34-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a3f34-106">\<trackingProfile></span></span>  
<span data-ttu-id="a3f34-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a3f34-107">\<workflow></span></span>  
<span data-ttu-id="a3f34-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a3f34-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="a3f34-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a3f34-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f34-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3f34-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3f34-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3f34-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a3f34-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3f34-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3f34-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3f34-113">Attributes</span></span>  
 <span data-ttu-id="a3f34-114">Keine</span><span class="sxs-lookup"><span data-stu-id="a3f34-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3f34-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3f34-115">Child Elements</span></span>  
  
|<span data-ttu-id="a3f34-116">Element</span><span class="sxs-lookup"><span data-stu-id="a3f34-116">Element</span></span>|<span data-ttu-id="a3f34-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3f34-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3f34-118">\<states></span><span class="sxs-lookup"><span data-stu-id="a3f34-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="a3f34-119">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="a3f34-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3f34-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3f34-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a3f34-121">Element</span><span class="sxs-lookup"><span data-stu-id="a3f34-121">Element</span></span>|<span data-ttu-id="a3f34-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3f34-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3f34-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a3f34-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="a3f34-124">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a3f34-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f34-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3f34-125">Remarks</span></span>  
 <span data-ttu-id="a3f34-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="a3f34-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a3f34-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3f34-127">Example</span></span>  
 <span data-ttu-id="a3f34-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="a3f34-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3f34-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3f34-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a3f34-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a3f34-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a3f34-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a3f34-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

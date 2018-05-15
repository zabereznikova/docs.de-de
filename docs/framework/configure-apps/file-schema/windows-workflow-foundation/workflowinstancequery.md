---
title: '&lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: eb8b84f70025df3a8a8ac96f61dec6755eb3a364
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="3c2d5-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3c2d5-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="3c2d5-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3c2d5-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="3c2d5-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3c2d5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3c2d5-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c2d5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3c2d5-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3c2d5-106">\<tracking></span></span>  
<span data-ttu-id="3c2d5-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3c2d5-107">\<trackingProfile></span></span>  
<span data-ttu-id="3c2d5-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3c2d5-108">\<workflow></span></span>  
<span data-ttu-id="3c2d5-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="3c2d5-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="3c2d5-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="3c2d5-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c2d5-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c2d5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c2d5-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c2d5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c2d5-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c2d5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c2d5-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c2d5-114">Attributes</span></span>  
 <span data-ttu-id="3c2d5-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3c2d5-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c2d5-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c2d5-116">Child Elements</span></span>  
  
|<span data-ttu-id="3c2d5-117">Element</span><span class="sxs-lookup"><span data-stu-id="3c2d5-117">Element</span></span>|<span data-ttu-id="3c2d5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c2d5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c2d5-119">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="3c2d5-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3c2d5-120">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="3c2d5-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c2d5-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c2d5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3c2d5-122">Element</span><span class="sxs-lookup"><span data-stu-id="3c2d5-122">Element</span></span>|<span data-ttu-id="3c2d5-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c2d5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c2d5-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="3c2d5-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="3c2d5-125">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3c2d5-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c2d5-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c2d5-126">Remarks</span></span>  
 <span data-ttu-id="3c2d5-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="3c2d5-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="3c2d5-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c2d5-128">Example</span></span>  
 <span data-ttu-id="3c2d5-129">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="3c2d5-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c2d5-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c2d5-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="3c2d5-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3c2d5-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3c2d5-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3c2d5-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;workflowInstanceQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: c3b68dda42fd7a9356366a0887feb359d0232b32
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="b1777-102">&lt;workflowInstanceQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="b1777-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="b1777-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b1777-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="b1777-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b1777-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="b1777-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b1777-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b1777-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="b1777-106">\<tracking></span></span>  
<span data-ttu-id="b1777-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b1777-107">\<trackingProfile></span></span>  
<span data-ttu-id="b1777-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b1777-108">\<workflow></span></span>  
<span data-ttu-id="b1777-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b1777-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b1777-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="b1777-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1777-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1777-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1777-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1777-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b1777-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1777-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1777-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1777-114">Attributes</span></span>  
 <span data-ttu-id="b1777-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b1777-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1777-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1777-116">Child Elements</span></span>  
  
|<span data-ttu-id="b1777-117">Element</span><span class="sxs-lookup"><span data-stu-id="b1777-117">Element</span></span>|<span data-ttu-id="b1777-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1777-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1777-119">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="b1777-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="b1777-120">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="b1777-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1777-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1777-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b1777-122">Element</span><span class="sxs-lookup"><span data-stu-id="b1777-122">Element</span></span>|<span data-ttu-id="b1777-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1777-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1777-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b1777-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="b1777-125">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b1777-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1777-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1777-126">Remarks</span></span>  
 <span data-ttu-id="b1777-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="b1777-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b1777-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1777-128">Example</span></span>  
 <span data-ttu-id="b1777-129">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="b1777-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1777-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1777-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="b1777-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b1777-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b1777-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b1777-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

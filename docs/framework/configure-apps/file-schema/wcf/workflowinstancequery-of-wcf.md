---
title: <workflowInstanceQuery> von WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 726d4db3bad9f57663790e2bb4e081faba28f1ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672964"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="1ecb2-102">\<WorkflowInstanceQuery > von WCF</span><span class="sxs-lookup"><span data-stu-id="1ecb2-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="1ecb2-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1ecb2-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="1ecb2-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1ecb2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1ecb2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1ecb2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1ecb2-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1ecb2-106">\<tracking></span></span>  
<span data-ttu-id="1ecb2-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="1ecb2-107">\<profiles></span></span>  
<span data-ttu-id="1ecb2-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1ecb2-108">\<trackingProfile></span></span>  
<span data-ttu-id="1ecb2-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1ecb2-109">\<workflow></span></span>  
<span data-ttu-id="1ecb2-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="1ecb2-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="1ecb2-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="1ecb2-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ecb2-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ecb2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ecb2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecb2-113">Attributes and elements</span></span>  

<span data-ttu-id="1ecb2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ecb2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ecb2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ecb2-115">Attributes</span></span>  

<span data-ttu-id="1ecb2-116">Keine</span><span class="sxs-lookup"><span data-stu-id="1ecb2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ecb2-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecb2-117">Child elements</span></span>  
  
|<span data-ttu-id="1ecb2-118">Element</span><span class="sxs-lookup"><span data-stu-id="1ecb2-118">Element</span></span>|<span data-ttu-id="1ecb2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ecb2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ecb2-120">\<states></span><span class="sxs-lookup"><span data-stu-id="1ecb2-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="1ecb2-121">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="1ecb2-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ecb2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecb2-122">Parent elements</span></span>  
  
|<span data-ttu-id="1ecb2-123">Element</span><span class="sxs-lookup"><span data-stu-id="1ecb2-123">Element</span></span>|<span data-ttu-id="1ecb2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ecb2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ecb2-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="1ecb2-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="1ecb2-126">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1ecb2-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ecb2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ecb2-127">Remarks</span></span>  

<span data-ttu-id="1ecb2-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="1ecb2-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="1ecb2-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ecb2-129">Example</span></span>  

<span data-ttu-id="1ecb2-130">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="1ecb2-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="1ecb2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ecb2-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ecb2-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1ecb2-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ecb2-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1ecb2-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

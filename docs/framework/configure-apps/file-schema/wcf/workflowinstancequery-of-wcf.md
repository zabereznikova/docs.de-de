---
title: '&lt;workflowInstanceQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 01867171941db82260d28b0825bdf3453e46e66c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148174"
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="b110f-102">&lt;workflowInstanceQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="b110f-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>

<span data-ttu-id="b110f-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b110f-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="b110f-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b110f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b110f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b110f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b110f-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="b110f-106">\<tracking></span></span>  
<span data-ttu-id="b110f-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="b110f-107">\<profiles></span></span>  
<span data-ttu-id="b110f-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b110f-108">\<trackingProfile></span></span>  
<span data-ttu-id="b110f-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b110f-109">\<workflow></span></span>  
<span data-ttu-id="b110f-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b110f-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b110f-111">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="b110f-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b110f-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="b110f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b110f-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b110f-113">Attributes and elements</span></span>  

<span data-ttu-id="b110f-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b110f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b110f-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="b110f-115">Attributes</span></span>  

<span data-ttu-id="b110f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b110f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b110f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b110f-117">Child elements</span></span>  
  
|<span data-ttu-id="b110f-118">Element</span><span class="sxs-lookup"><span data-stu-id="b110f-118">Element</span></span>|<span data-ttu-id="b110f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b110f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b110f-120">\<Status ></span><span class="sxs-lookup"><span data-stu-id="b110f-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="b110f-121">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="b110f-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b110f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b110f-122">Parent elements</span></span>  
  
|<span data-ttu-id="b110f-123">Element</span><span class="sxs-lookup"><span data-stu-id="b110f-123">Element</span></span>|<span data-ttu-id="b110f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b110f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b110f-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b110f-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="b110f-126">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b110f-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b110f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b110f-127">Remarks</span></span>  

<span data-ttu-id="b110f-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="b110f-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b110f-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b110f-129">Example</span></span>  

<span data-ttu-id="b110f-130">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="b110f-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="b110f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b110f-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b110f-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b110f-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b110f-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b110f-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

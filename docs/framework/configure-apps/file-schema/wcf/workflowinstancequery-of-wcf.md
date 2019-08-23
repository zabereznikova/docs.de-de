---
title: <workflowInstanceQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 7e15d7654aeafa5fa7b87922283d6520d5493242
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915224"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="d5231-102">\<WorkflowInstanceQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="d5231-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="d5231-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d5231-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="d5231-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d5231-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d5231-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d5231-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d5231-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="d5231-106">\<tracking></span></span>  
<span data-ttu-id="d5231-107">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="d5231-107">\<profiles></span></span>  
<span data-ttu-id="d5231-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d5231-108">\<trackingProfile></span></span>  
<span data-ttu-id="d5231-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d5231-109">\<workflow></span></span>  
<span data-ttu-id="d5231-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="d5231-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="d5231-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="d5231-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5231-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5231-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5231-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5231-113">Attributes and elements</span></span>  

<span data-ttu-id="d5231-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5231-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5231-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5231-115">Attributes</span></span>  

<span data-ttu-id="d5231-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d5231-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5231-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5231-117">Child elements</span></span>  
  
|<span data-ttu-id="d5231-118">Element</span><span class="sxs-lookup"><span data-stu-id="d5231-118">Element</span></span>|<span data-ttu-id="d5231-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5231-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5231-120">\<Status ></span><span class="sxs-lookup"><span data-stu-id="d5231-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="d5231-121">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="d5231-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5231-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5231-122">Parent elements</span></span>  
  
|<span data-ttu-id="d5231-123">Element</span><span class="sxs-lookup"><span data-stu-id="d5231-123">Element</span></span>|<span data-ttu-id="d5231-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5231-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5231-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="d5231-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="d5231-126">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d5231-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5231-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5231-127">Remarks</span></span>  

<span data-ttu-id="d5231-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="d5231-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="d5231-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5231-129">Example</span></span>  

<span data-ttu-id="d5231-130">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="d5231-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="d5231-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5231-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d5231-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d5231-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5231-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d5231-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

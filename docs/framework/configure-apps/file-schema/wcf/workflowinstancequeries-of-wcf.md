---
title: <workflowInstanceQueries> von WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 544ca868485a409554ece9d9b000beb1a472d344
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255301"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="ba51f-102">\<WorkflowInstanceQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="ba51f-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="ba51f-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ba51f-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="ba51f-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ba51f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ba51f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba51f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ba51f-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ba51f-106">\<tracking></span></span>  
<span data-ttu-id="ba51f-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="ba51f-107">\<profiles></span></span>  
<span data-ttu-id="ba51f-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ba51f-108">\<trackingProfile></span></span>  
<span data-ttu-id="ba51f-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ba51f-109">\<workflow></span></span>  
<span data-ttu-id="ba51f-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="ba51f-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba51f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba51f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba51f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba51f-112">Attributes and elements</span></span>

<span data-ttu-id="ba51f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba51f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba51f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba51f-114">Attributes</span></span>  

<span data-ttu-id="ba51f-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ba51f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba51f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba51f-116">Child elements</span></span>  
  
|<span data-ttu-id="ba51f-117">Element</span><span class="sxs-lookup"><span data-stu-id="ba51f-117">Element</span></span>|<span data-ttu-id="ba51f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba51f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba51f-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="ba51f-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="ba51f-120">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba51f-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba51f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba51f-121">Parent elements</span></span>  
  
|<span data-ttu-id="ba51f-122">Element</span><span class="sxs-lookup"><span data-stu-id="ba51f-122">Element</span></span>|<span data-ttu-id="ba51f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba51f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba51f-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ba51f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ba51f-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die [ActivityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ba51f-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba51f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba51f-126">Remarks</span></span>

<span data-ttu-id="ba51f-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="ba51f-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="ba51f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba51f-128">Example</span></span>  

<span data-ttu-id="ba51f-129">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="ba51f-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba51f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba51f-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ba51f-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ba51f-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ba51f-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ba51f-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;workflowInstanceQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 8ee8c74e88f1605ae3858db787c38976de9cc976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693703"
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="62040-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="62040-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="62040-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="62040-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="62040-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="62040-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="62040-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62040-105">\<system.serviceModel></span></span>  
<span data-ttu-id="62040-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="62040-106">\<tracking></span></span>  
<span data-ttu-id="62040-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="62040-107">\<trackingProfile></span></span>  
<span data-ttu-id="62040-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="62040-108">\<workflow></span></span>  
<span data-ttu-id="62040-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="62040-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62040-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="62040-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62040-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62040-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62040-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62040-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62040-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="62040-113">Attributes</span></span>  
 <span data-ttu-id="62040-114">Keine</span><span class="sxs-lookup"><span data-stu-id="62040-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62040-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62040-115">Child Elements</span></span>  
  
|<span data-ttu-id="62040-116">Element</span><span class="sxs-lookup"><span data-stu-id="62040-116">Element</span></span>|<span data-ttu-id="62040-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62040-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62040-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="62040-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="62040-119">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="62040-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62040-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62040-120">Parent Elements</span></span>  
  
|<span data-ttu-id="62040-121">Element</span><span class="sxs-lookup"><span data-stu-id="62040-121">Element</span></span>|<span data-ttu-id="62040-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62040-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62040-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="62040-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="62040-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="62040-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62040-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62040-125">Remarks</span></span>  
 <span data-ttu-id="62040-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="62040-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="62040-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62040-127">Example</span></span>  
 <span data-ttu-id="62040-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="62040-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62040-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62040-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="62040-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="62040-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="62040-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="62040-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

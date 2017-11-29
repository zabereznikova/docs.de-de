---
title: '&lt;workflowInstanceQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 182a4082de6f1c67b7a0bc26662e2491623b2bba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="a108b-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a108b-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="a108b-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a108b-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="a108b-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a108b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a108b-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a108b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a108b-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a108b-106">\<tracking></span></span>  
<span data-ttu-id="a108b-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a108b-107">\<trackingProfile></span></span>  
<span data-ttu-id="a108b-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a108b-108">\<workflow></span></span>  
<span data-ttu-id="a108b-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="a108b-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a108b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a108b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a108b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a108b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a108b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a108b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a108b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a108b-113">Attributes</span></span>  
 <span data-ttu-id="a108b-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="a108b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a108b-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a108b-115">Child Elements</span></span>  
  
|<span data-ttu-id="a108b-116">Element</span><span class="sxs-lookup"><span data-stu-id="a108b-116">Element</span></span>|<span data-ttu-id="a108b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a108b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a108b-118">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="a108b-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="a108b-119">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a108b-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a108b-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a108b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a108b-121">Element</span><span class="sxs-lookup"><span data-stu-id="a108b-121">Element</span></span>|<span data-ttu-id="a108b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a108b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a108b-123">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a108b-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a108b-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a108b-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a108b-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a108b-125">Remarks</span></span>  
 <span data-ttu-id="a108b-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="a108b-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a108b-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a108b-127">Example</span></span>  
 <span data-ttu-id="a108b-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="a108b-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a108b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a108b-129">See Also</span></span>  
 <span data-ttu-id="a108b-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a108b-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a108b-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a108b-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a108b-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a108b-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a108b-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a108b-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

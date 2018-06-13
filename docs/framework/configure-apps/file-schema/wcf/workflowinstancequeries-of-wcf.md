---
title: '&lt;workflowInstanceQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 02bb0be83158fddf5907465db5a12a4708461ecb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767458"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="403f8-102">&lt;workflowInstanceQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="403f8-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="403f8-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="403f8-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="403f8-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="403f8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="403f8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="403f8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="403f8-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="403f8-106">\<tracking></span></span>  
<span data-ttu-id="403f8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="403f8-107">\<trackingProfile></span></span>  
<span data-ttu-id="403f8-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="403f8-108">\<workflow></span></span>  
<span data-ttu-id="403f8-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="403f8-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="403f8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="403f8-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="403f8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="403f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="403f8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="403f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="403f8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="403f8-113">Attributes</span></span>  
 <span data-ttu-id="403f8-114">Keine</span><span class="sxs-lookup"><span data-stu-id="403f8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="403f8-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="403f8-115">Child Elements</span></span>  
  
|<span data-ttu-id="403f8-116">Element</span><span class="sxs-lookup"><span data-stu-id="403f8-116">Element</span></span>|<span data-ttu-id="403f8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="403f8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="403f8-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="403f8-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="403f8-119">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="403f8-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="403f8-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="403f8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="403f8-121">Element</span><span class="sxs-lookup"><span data-stu-id="403f8-121">Element</span></span>|<span data-ttu-id="403f8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="403f8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="403f8-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="403f8-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="403f8-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die [ActivityDefinitionId](http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="403f8-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="403f8-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="403f8-125">Remarks</span></span>  
 <span data-ttu-id="403f8-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="403f8-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="403f8-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="403f8-127">Example</span></span>  
 <span data-ttu-id="403f8-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="403f8-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="403f8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="403f8-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="403f8-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="403f8-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="403f8-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="403f8-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

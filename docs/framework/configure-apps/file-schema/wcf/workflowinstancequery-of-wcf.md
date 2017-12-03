---
title: '&lt;workflowInstanceQuery&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64b404fec3f3cd46912deede61bf08f8e962f1d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="712c9-102">&lt;workflowInstanceQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="712c9-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="712c9-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="712c9-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="712c9-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="712c9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="712c9-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="712c9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="712c9-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="712c9-106">\<tracking></span></span>  
<span data-ttu-id="712c9-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="712c9-107">\<trackingProfile></span></span>  
<span data-ttu-id="712c9-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="712c9-108">\<workflow></span></span>  
<span data-ttu-id="712c9-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="712c9-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="712c9-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="712c9-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="712c9-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="712c9-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="712c9-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="712c9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="712c9-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="712c9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="712c9-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="712c9-114">Attributes</span></span>  
 <span data-ttu-id="712c9-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="712c9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="712c9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="712c9-116">Child Elements</span></span>  
  
|<span data-ttu-id="712c9-117">Element</span><span class="sxs-lookup"><span data-stu-id="712c9-117">Element</span></span>|<span data-ttu-id="712c9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="712c9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="712c9-119">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="712c9-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="712c9-120">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="712c9-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="712c9-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="712c9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="712c9-122">Element</span><span class="sxs-lookup"><span data-stu-id="712c9-122">Element</span></span>|<span data-ttu-id="712c9-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="712c9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="712c9-124">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="712c9-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="712c9-125">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="712c9-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="712c9-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="712c9-126">Remarks</span></span>  
 <span data-ttu-id="712c9-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="712c9-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="712c9-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="712c9-128">Example</span></span>  
 <span data-ttu-id="712c9-129">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="712c9-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="712c9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="712c9-130">See Also</span></span>  
 <span data-ttu-id="712c9-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="712c9-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="712c9-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="712c9-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="712c9-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="712c9-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="712c9-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="712c9-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

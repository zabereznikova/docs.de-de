---
title: '&lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7d9d19c4ea5ecd5dc7a7329eb3fdad657567864
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="1a16e-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="1a16e-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="1a16e-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1a16e-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="1a16e-104">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1a16e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1a16e-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1a16e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1a16e-106">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="1a16e-106">\<tracking></span></span>  
<span data-ttu-id="1a16e-107">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1a16e-107">\<trackingProfile></span></span>  
<span data-ttu-id="1a16e-108">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="1a16e-108">\<workflow></span></span>  
<span data-ttu-id="1a16e-109">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="1a16e-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="1a16e-110">\<WorkflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="1a16e-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a16e-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a16e-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a16e-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1a16e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1a16e-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a16e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a16e-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="1a16e-114">Attributes</span></span>  
 <span data-ttu-id="1a16e-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="1a16e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a16e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a16e-116">Child Elements</span></span>  
  
|<span data-ttu-id="1a16e-117">Element</span><span class="sxs-lookup"><span data-stu-id="1a16e-117">Element</span></span>|<span data-ttu-id="1a16e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a16e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a16e-119">\<Zustände ></span><span class="sxs-lookup"><span data-stu-id="1a16e-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="1a16e-120">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="1a16e-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a16e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a16e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1a16e-122">Element</span><span class="sxs-lookup"><span data-stu-id="1a16e-122">Element</span></span>|<span data-ttu-id="1a16e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a16e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a16e-124">\<WorkflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="1a16e-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="1a16e-125">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1a16e-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a16e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a16e-126">Remarks</span></span>  
 <span data-ttu-id="1a16e-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="1a16e-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="1a16e-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a16e-128">Example</span></span>  
 <span data-ttu-id="1a16e-129">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="1a16e-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a16e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a16e-130">See Also</span></span>  
 <span data-ttu-id="1a16e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1a16e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1a16e-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1a16e-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1a16e-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1a16e-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1a16e-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1a16e-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

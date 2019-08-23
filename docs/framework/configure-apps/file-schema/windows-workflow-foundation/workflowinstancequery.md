---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: f0a3c3a27b40000432b40b7008f81251fe771ca2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913144"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="51267-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="51267-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="51267-102">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="51267-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="51267-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="51267-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="51267-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="51267-104">\<system.serviceModel></span></span>  
<span data-ttu-id="51267-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="51267-105">\<tracking></span></span>  
<span data-ttu-id="51267-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="51267-106">\<trackingProfile></span></span>  
<span data-ttu-id="51267-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="51267-107">\<workflow></span></span>  
<span data-ttu-id="51267-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="51267-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="51267-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="51267-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51267-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="51267-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51267-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="51267-111">Attributes and Elements</span></span>  
 <span data-ttu-id="51267-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="51267-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51267-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="51267-113">Attributes</span></span>  
 <span data-ttu-id="51267-114">Keine</span><span class="sxs-lookup"><span data-stu-id="51267-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51267-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51267-115">Child Elements</span></span>  
  
|<span data-ttu-id="51267-116">Element</span><span class="sxs-lookup"><span data-stu-id="51267-116">Element</span></span>|<span data-ttu-id="51267-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51267-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51267-118">\<Status ></span><span class="sxs-lookup"><span data-stu-id="51267-118">\<states></span></span>](states.md)|<span data-ttu-id="51267-119">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="51267-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51267-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51267-120">Parent Elements</span></span>  
  
|<span data-ttu-id="51267-121">Element</span><span class="sxs-lookup"><span data-stu-id="51267-121">Element</span></span>|<span data-ttu-id="51267-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51267-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51267-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="51267-123">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="51267-124">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="51267-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51267-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51267-125">Remarks</span></span>  
 <span data-ttu-id="51267-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="51267-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="51267-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51267-127">Example</span></span>  
 <span data-ttu-id="51267-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="51267-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="51267-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51267-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="51267-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="51267-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="51267-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="51267-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

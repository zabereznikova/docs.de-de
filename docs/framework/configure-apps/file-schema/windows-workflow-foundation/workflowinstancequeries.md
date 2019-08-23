---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 0a32e6ee22cdf984e64c1b8fa16836c4c56d0380
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932739"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="8a114-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="8a114-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="8a114-102">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="8a114-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="8a114-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="8a114-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8a114-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8a114-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8a114-105">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="8a114-105">\<tracking></span></span>  
<span data-ttu-id="8a114-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8a114-106">\<trackingProfile></span></span>  
<span data-ttu-id="8a114-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8a114-107">\<workflow></span></span>  
<span data-ttu-id="8a114-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="8a114-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a114-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a114-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a114-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a114-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8a114-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a114-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a114-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a114-112">Attributes</span></span>  
 <span data-ttu-id="8a114-113">Keine</span><span class="sxs-lookup"><span data-stu-id="8a114-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a114-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a114-114">Child Elements</span></span>  
  
|<span data-ttu-id="8a114-115">Element</span><span class="sxs-lookup"><span data-stu-id="8a114-115">Element</span></span>|<span data-ttu-id="8a114-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a114-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a114-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="8a114-117">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="8a114-118">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8a114-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a114-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a114-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8a114-120">Element</span><span class="sxs-lookup"><span data-stu-id="8a114-120">Element</span></span>|<span data-ttu-id="8a114-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a114-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a114-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8a114-122">\<workflow></span></span>](workflow.md)|<span data-ttu-id="8a114-123">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8a114-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a114-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a114-124">Remarks</span></span>  
 <span data-ttu-id="8a114-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="8a114-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="8a114-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a114-126">Example</span></span>  
 <span data-ttu-id="8a114-127">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="8a114-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a114-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a114-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8a114-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8a114-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8a114-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8a114-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

---
title: <workflowInstanceQueries>von WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854771"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="34701-102">\<workflowinstancequeries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="34701-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="34701-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="34701-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="34701-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="34701-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="34701-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34701-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34701-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="34701-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="34701-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="34701-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="34701-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="34701-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="34701-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="34701-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="34701-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="34701-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="34701-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowinstancequeries->**</span><span class="sxs-lookup"><span data-stu-id="34701-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34701-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="34701-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34701-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34701-113">Attributes and elements</span></span>

<span data-ttu-id="34701-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34701-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34701-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="34701-115">Attributes</span></span>  

<span data-ttu-id="34701-116">Keine</span><span class="sxs-lookup"><span data-stu-id="34701-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34701-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34701-117">Child elements</span></span>  
  
|<span data-ttu-id="34701-118">Element</span><span class="sxs-lookup"><span data-stu-id="34701-118">Element</span></span>|<span data-ttu-id="34701-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34701-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34701-120">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="34701-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="34701-121">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="34701-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34701-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34701-122">Parent elements</span></span>  
  
|<span data-ttu-id="34701-123">Element</span><span class="sxs-lookup"><span data-stu-id="34701-123">Element</span></span>|<span data-ttu-id="34701-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34701-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34701-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="34701-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="34701-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="34701-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34701-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34701-127">Remarks</span></span>

<span data-ttu-id="34701-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="34701-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="34701-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34701-129">Example</span></span>  

<span data-ttu-id="34701-130">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="34701-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="34701-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34701-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="34701-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="34701-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="34701-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="34701-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

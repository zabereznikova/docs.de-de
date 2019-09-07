---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398579"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="fe3aa-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="fe3aa-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="fe3aa-102">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fe3aa-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="fe3aa-103">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="fe3aa-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fe3aa-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe3aa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe3aa-105">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe3aa-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="fe3aa-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="fe3aa-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="fe3aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="fe3aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="fe3aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fe3aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="fe3aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowinstancequeries->**</span><span class="sxs-lookup"><span data-stu-id="fe3aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe3aa-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe3aa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe3aa-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3aa-111">Attributes and Elements</span></span>  

<span data-ttu-id="fe3aa-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe3aa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe3aa-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe3aa-113">Attributes</span></span>  

<span data-ttu-id="fe3aa-114">Keine</span><span class="sxs-lookup"><span data-stu-id="fe3aa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe3aa-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3aa-115">Child Elements</span></span>  
  
|<span data-ttu-id="fe3aa-116">Element</span><span class="sxs-lookup"><span data-stu-id="fe3aa-116">Element</span></span>|<span data-ttu-id="fe3aa-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3aa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe3aa-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="fe3aa-118">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="fe3aa-119">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="fe3aa-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe3aa-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3aa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fe3aa-121">Element</span><span class="sxs-lookup"><span data-stu-id="fe3aa-121">Element</span></span>|<span data-ttu-id="fe3aa-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3aa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe3aa-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="fe3aa-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="fe3aa-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="fe3aa-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe3aa-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe3aa-125">Remarks</span></span>  

<span data-ttu-id="fe3aa-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="fe3aa-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="fe3aa-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe3aa-127">Example</span></span>  

<span data-ttu-id="fe3aa-128">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="fe3aa-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe3aa-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe3aa-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fe3aa-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="fe3aa-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fe3aa-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="fe3aa-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

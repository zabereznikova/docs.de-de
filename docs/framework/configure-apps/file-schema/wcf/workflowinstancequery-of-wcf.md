---
title: <workflowInstanceQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854738"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="95365-102">\<WorkflowInstanceQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="95365-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="95365-103">Stellt eine Abfrage dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="95365-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="95365-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="95365-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="95365-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="95365-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="95365-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="95365-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="95365-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="95365-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="95365-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="95365-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="95365-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="95365-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="95365-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="95365-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="95365-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowinstancequeries->** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="95365-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="95365-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WorkflowInstanceQuery->**</span><span class="sxs-lookup"><span data-stu-id="95365-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95365-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="95365-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95365-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="95365-114">Attributes and elements</span></span>  

<span data-ttu-id="95365-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95365-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95365-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="95365-116">Attributes</span></span>  

<span data-ttu-id="95365-117">Keine</span><span class="sxs-lookup"><span data-stu-id="95365-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95365-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95365-118">Child elements</span></span>  
  
|<span data-ttu-id="95365-119">Element</span><span class="sxs-lookup"><span data-stu-id="95365-119">Element</span></span>|<span data-ttu-id="95365-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95365-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95365-121">\<Status ></span><span class="sxs-lookup"><span data-stu-id="95365-121">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="95365-122">Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="95365-122">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95365-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95365-123">Parent elements</span></span>  
  
|<span data-ttu-id="95365-124">Element</span><span class="sxs-lookup"><span data-stu-id="95365-124">Element</span></span>|<span data-ttu-id="95365-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95365-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95365-126">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="95365-126">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="95365-127">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="95365-127">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95365-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95365-128">Remarks</span></span>  

<span data-ttu-id="95365-129"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="95365-129">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="95365-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95365-130">Example</span></span>  

<span data-ttu-id="95365-131">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="95365-131">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="95365-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95365-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="95365-133">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="95365-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="95365-134">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="95365-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

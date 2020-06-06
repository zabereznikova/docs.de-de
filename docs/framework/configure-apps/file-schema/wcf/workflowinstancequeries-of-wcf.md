---
title: <workflowInstanceQueries>von WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854771"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="bf3e0-102">\<workflowInstanceQueries>von WCF</span><span class="sxs-lookup"><span data-stu-id="bf3e0-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="bf3e0-103">Stellt eine Auflistung von Konfigurationselementen dar, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgen, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bf3e0-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="bf3e0-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="bf3e0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="bf3e0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf3e0-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf3e0-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf3e0-106">Attributes and elements</span></span>

<span data-ttu-id="bf3e0-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf3e0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf3e0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf3e0-108">Attributes</span></span>  

<span data-ttu-id="bf3e0-109">Keine</span><span class="sxs-lookup"><span data-stu-id="bf3e0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf3e0-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf3e0-110">Child elements</span></span>  
  
|<span data-ttu-id="bf3e0-111">Element</span><span class="sxs-lookup"><span data-stu-id="bf3e0-111">Element</span></span>|<span data-ttu-id="bf3e0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bf3e0-112">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="bf3e0-113">Eine Abfrage, die verwendet wird, um Änderungen im Lebenszyklus einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="bf3e0-113">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf3e0-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf3e0-114">Parent elements</span></span>  
  
|<span data-ttu-id="bf3e0-115">Element</span><span class="sxs-lookup"><span data-stu-id="bf3e0-115">Element</span></span>|<span data-ttu-id="bf3e0-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bf3e0-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="bf3e0-117">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="bf3e0-117">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf3e0-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bf3e0-118">Remarks</span></span>

<span data-ttu-id="bf3e0-119"><xref:System.Activities.Tracking.WorkflowInstanceQuery> – Wird für das Abonnieren der folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekte verwendet:</span><span class="sxs-lookup"><span data-stu-id="bf3e0-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="bf3e0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf3e0-120">Example</span></span>  

<span data-ttu-id="bf3e0-121">In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.</span><span class="sxs-lookup"><span data-stu-id="bf3e0-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="bf3e0-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf3e0-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bf3e0-123">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="bf3e0-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bf3e0-124">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="bf3e0-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

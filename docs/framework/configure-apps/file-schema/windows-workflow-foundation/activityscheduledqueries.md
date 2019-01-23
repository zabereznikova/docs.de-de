---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 2285dfae84f078483c03d85801051e29b79e74c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561841"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="afbb4-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="afbb4-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="afbb4-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="afbb4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="afbb4-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="afbb4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="afbb4-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="afbb4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="afbb4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="afbb4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="afbb4-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="afbb4-107">\<tracking></span></span>  
<span data-ttu-id="afbb4-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="afbb4-108">\<trackingProfile></span></span>  
<span data-ttu-id="afbb4-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="afbb4-109">\<workflow></span></span>  
<span data-ttu-id="afbb4-110">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="afbb4-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbb4-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="afbb4-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afbb4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="afbb4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="afbb4-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afbb4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afbb4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="afbb4-114">Attributes</span></span>  
 <span data-ttu-id="afbb4-115">Keine</span><span class="sxs-lookup"><span data-stu-id="afbb4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="afbb4-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afbb4-116">Child Elements</span></span>  
  
|<span data-ttu-id="afbb4-117">Element</span><span class="sxs-lookup"><span data-stu-id="afbb4-117">Element</span></span>|<span data-ttu-id="afbb4-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afbb4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afbb4-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="afbb4-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="afbb4-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="afbb4-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afbb4-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afbb4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="afbb4-122">Element</span><span class="sxs-lookup"><span data-stu-id="afbb4-122">Element</span></span>|<span data-ttu-id="afbb4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afbb4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afbb4-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="afbb4-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="afbb4-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="afbb4-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afbb4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afbb4-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="afbb4-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="afbb4-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="afbb4-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="afbb4-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

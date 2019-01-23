---
title: '&lt;activityScheduledQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 5430058049e8a09c1e2a289e1f997338c23b9d94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492155"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="33bfa-102">&lt;activityScheduledQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="33bfa-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="33bfa-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="33bfa-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="33bfa-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="33bfa-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="33bfa-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="33bfa-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="33bfa-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="33bfa-106">\<system.serviceModel></span></span>  
<span data-ttu-id="33bfa-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="33bfa-107">\<tracking></span></span>  
<span data-ttu-id="33bfa-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="33bfa-108">\<profiles></span></span>  
<span data-ttu-id="33bfa-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="33bfa-109">\<trackingProfile></span></span>  
<span data-ttu-id="33bfa-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="33bfa-110">\<workflow></span></span>  
<span data-ttu-id="33bfa-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="33bfa-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bfa-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="33bfa-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33bfa-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="33bfa-113">Attributes and elements</span></span>  

<span data-ttu-id="33bfa-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33bfa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33bfa-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="33bfa-115">Attributes</span></span>  

<span data-ttu-id="33bfa-116">Keine</span><span class="sxs-lookup"><span data-stu-id="33bfa-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33bfa-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33bfa-117">Child elements</span></span>  
  
|<span data-ttu-id="33bfa-118">Element</span><span class="sxs-lookup"><span data-stu-id="33bfa-118">Element</span></span>|<span data-ttu-id="33bfa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33bfa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33bfa-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="33bfa-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="33bfa-121">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="33bfa-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33bfa-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33bfa-122">Parent elements</span></span>  
  
|<span data-ttu-id="33bfa-123">Element</span><span class="sxs-lookup"><span data-stu-id="33bfa-123">Element</span></span>|<span data-ttu-id="33bfa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33bfa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33bfa-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="33bfa-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="33bfa-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="33bfa-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33bfa-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33bfa-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="33bfa-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="33bfa-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="33bfa-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="33bfa-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

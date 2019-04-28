---
title: <activityScheduledQueries> von WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 1c9c292080016d7a2d0014ed07be371c0e247621
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701124"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="ce2a2-102">\<ActivityScheduledQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="ce2a2-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="ce2a2-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ce2a2-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ce2a2-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ce2a2-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="ce2a2-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ce2a2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ce2a2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce2a2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ce2a2-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ce2a2-107">\<tracking></span></span>  
<span data-ttu-id="ce2a2-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="ce2a2-108">\<profiles></span></span>  
<span data-ttu-id="ce2a2-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ce2a2-109">\<trackingProfile></span></span>  
<span data-ttu-id="ce2a2-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ce2a2-110">\<workflow></span></span>  
<span data-ttu-id="ce2a2-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="ce2a2-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce2a2-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce2a2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce2a2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce2a2-113">Attributes and elements</span></span>  

<span data-ttu-id="ce2a2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce2a2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce2a2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce2a2-115">Attributes</span></span>  

<span data-ttu-id="ce2a2-116">Keine</span><span class="sxs-lookup"><span data-stu-id="ce2a2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce2a2-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce2a2-117">Child elements</span></span>  
  
|<span data-ttu-id="ce2a2-118">Element</span><span class="sxs-lookup"><span data-stu-id="ce2a2-118">Element</span></span>|<span data-ttu-id="ce2a2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce2a2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce2a2-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="ce2a2-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="ce2a2-121">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ce2a2-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce2a2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce2a2-122">Parent elements</span></span>  
  
|<span data-ttu-id="ce2a2-123">Element</span><span class="sxs-lookup"><span data-stu-id="ce2a2-123">Element</span></span>|<span data-ttu-id="ce2a2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce2a2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce2a2-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ce2a2-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ce2a2-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ce2a2-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce2a2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce2a2-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="ce2a2-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ce2a2-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ce2a2-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ce2a2-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

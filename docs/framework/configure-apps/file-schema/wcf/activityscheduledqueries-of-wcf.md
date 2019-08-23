---
title: <activityScheduledQueries>von WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 83e71e2038377ae4c1c3b17334eece3f30c919f6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920322"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="b7e08-102">\<activityscheduledqueries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="b7e08-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="b7e08-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b7e08-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b7e08-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b7e08-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b7e08-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b7e08-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b7e08-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b7e08-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b7e08-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="b7e08-107">\<tracking></span></span>  
<span data-ttu-id="b7e08-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="b7e08-108">\<profiles></span></span>  
<span data-ttu-id="b7e08-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b7e08-109">\<trackingProfile></span></span>  
<span data-ttu-id="b7e08-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b7e08-110">\<workflow></span></span>  
<span data-ttu-id="b7e08-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b7e08-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e08-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7e08-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7e08-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7e08-113">Attributes and elements</span></span>  

<span data-ttu-id="b7e08-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7e08-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7e08-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7e08-115">Attributes</span></span>  

<span data-ttu-id="b7e08-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b7e08-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7e08-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7e08-117">Child elements</span></span>  
  
|<span data-ttu-id="b7e08-118">Element</span><span class="sxs-lookup"><span data-stu-id="b7e08-118">Element</span></span>|<span data-ttu-id="b7e08-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7e08-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7e08-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="b7e08-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="b7e08-121">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b7e08-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7e08-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7e08-122">Parent elements</span></span>  
  
|<span data-ttu-id="b7e08-123">Element</span><span class="sxs-lookup"><span data-stu-id="b7e08-123">Element</span></span>|<span data-ttu-id="b7e08-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7e08-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7e08-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b7e08-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b7e08-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b7e08-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7e08-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7e08-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b7e08-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b7e08-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b7e08-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b7e08-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

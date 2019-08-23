---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945534"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="4ccf1-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="4ccf1-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="4ccf1-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="4ccf1-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4ccf1-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="4ccf1-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="4ccf1-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4ccf1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4ccf1-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4ccf1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4ccf1-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="4ccf1-106">\<tracking></span></span>  
<span data-ttu-id="4ccf1-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4ccf1-107">\<trackingProfile></span></span>  
<span data-ttu-id="4ccf1-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4ccf1-108">\<workflow></span></span>  
<span data-ttu-id="4ccf1-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="4ccf1-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ccf1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ccf1-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ccf1-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ccf1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4ccf1-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ccf1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ccf1-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ccf1-113">Attributes</span></span>  
 <span data-ttu-id="4ccf1-114">Keine</span><span class="sxs-lookup"><span data-stu-id="4ccf1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4ccf1-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ccf1-115">Child Elements</span></span>  
  
|<span data-ttu-id="4ccf1-116">Element</span><span class="sxs-lookup"><span data-stu-id="4ccf1-116">Element</span></span>|<span data-ttu-id="4ccf1-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ccf1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ccf1-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="4ccf1-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="4ccf1-119">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="4ccf1-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ccf1-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ccf1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ccf1-121">Element</span><span class="sxs-lookup"><span data-stu-id="4ccf1-121">Element</span></span>|<span data-ttu-id="4ccf1-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ccf1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ccf1-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4ccf1-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="4ccf1-124">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="4ccf1-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ccf1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ccf1-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4ccf1-126">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="4ccf1-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4ccf1-127">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="4ccf1-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

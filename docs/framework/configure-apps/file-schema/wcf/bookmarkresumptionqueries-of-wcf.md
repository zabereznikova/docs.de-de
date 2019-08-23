---
title: <bookmarkResumptionQueries>von WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919744"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="16678-102">\<bookmarkresumptionqueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="16678-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="16678-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="16678-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="16678-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="16678-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="16678-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="16678-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="16678-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="16678-106">\<system.serviceModel></span></span>  
<span data-ttu-id="16678-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="16678-107">\<tracking></span></span>  
<span data-ttu-id="16678-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="16678-108">\<profiles></span></span>  
<span data-ttu-id="16678-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="16678-109">\<trackingProfile></span></span>  
<span data-ttu-id="16678-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="16678-110">\<workflow></span></span>  
<span data-ttu-id="16678-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="16678-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="16678-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="16678-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16678-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="16678-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16678-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16678-114">Attributes and elements</span></span>  
  
<span data-ttu-id="16678-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16678-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16678-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="16678-116">Attributes</span></span>  
  
<span data-ttu-id="16678-117">Keine</span><span class="sxs-lookup"><span data-stu-id="16678-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16678-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16678-118">Child elements</span></span>  
  
|<span data-ttu-id="16678-119">Element</span><span class="sxs-lookup"><span data-stu-id="16678-119">Element</span></span>|<span data-ttu-id="16678-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16678-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16678-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="16678-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="16678-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="16678-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="16678-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="16678-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16678-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16678-124">Parent elements</span></span>  
  
|<span data-ttu-id="16678-125">Element</span><span class="sxs-lookup"><span data-stu-id="16678-125">Element</span></span>|<span data-ttu-id="16678-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16678-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16678-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="16678-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="16678-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="16678-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16678-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16678-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="16678-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="16678-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="16678-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="16678-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

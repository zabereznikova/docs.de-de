---
title: <bookmarkResumptionQueries> von WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 4b11543e240b482d52c157083d1184db4f81bb04
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261268"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="a207a-102">\<BookmarkResumptionQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="a207a-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="a207a-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a207a-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a207a-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a207a-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="a207a-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a207a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a207a-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a207a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a207a-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a207a-107">\<tracking></span></span>  
<span data-ttu-id="a207a-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="a207a-108">\<profiles></span></span>  
<span data-ttu-id="a207a-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a207a-109">\<trackingProfile></span></span>  
<span data-ttu-id="a207a-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a207a-110">\<workflow></span></span>  
<span data-ttu-id="a207a-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a207a-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="a207a-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a207a-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a207a-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a207a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a207a-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a207a-114">Attributes and elements</span></span>  
  
<span data-ttu-id="a207a-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a207a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a207a-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a207a-116">Attributes</span></span>  
  
<span data-ttu-id="a207a-117">Keine</span><span class="sxs-lookup"><span data-stu-id="a207a-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a207a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a207a-118">Child elements</span></span>  
  
|<span data-ttu-id="a207a-119">Element</span><span class="sxs-lookup"><span data-stu-id="a207a-119">Element</span></span>|<span data-ttu-id="a207a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a207a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a207a-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a207a-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="a207a-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a207a-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a207a-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a207a-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a207a-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a207a-124">Parent elements</span></span>  
  
|<span data-ttu-id="a207a-125">Element</span><span class="sxs-lookup"><span data-stu-id="a207a-125">Element</span></span>|<span data-ttu-id="a207a-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a207a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a207a-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a207a-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a207a-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a207a-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a207a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a207a-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a207a-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a207a-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a207a-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a207a-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

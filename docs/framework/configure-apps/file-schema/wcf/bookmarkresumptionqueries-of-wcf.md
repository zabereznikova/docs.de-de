---
title: '&lt;bookmarkResumptionQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 80d1c1e4bc61972d44c27bcbdd0eba14d97c2d6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493949"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="ad227-102">&lt;bookmarkResumptionQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="ad227-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="ad227-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ad227-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ad227-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ad227-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="ad227-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ad227-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="ad227-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad227-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ad227-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ad227-107">\<tracking></span></span>  
<span data-ttu-id="ad227-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="ad227-108">\<profiles></span></span>  
<span data-ttu-id="ad227-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ad227-109">\<trackingProfile></span></span>  
<span data-ttu-id="ad227-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad227-110">\<workflow></span></span>  
<span data-ttu-id="ad227-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="ad227-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="ad227-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="ad227-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad227-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad227-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad227-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ad227-114">Attributes and elements</span></span>  
  
<span data-ttu-id="ad227-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad227-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad227-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="ad227-116">Attributes</span></span>  
  
<span data-ttu-id="ad227-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ad227-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad227-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad227-118">Child elements</span></span>  
  
|<span data-ttu-id="ad227-119">Element</span><span class="sxs-lookup"><span data-stu-id="ad227-119">Element</span></span>|<span data-ttu-id="ad227-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad227-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad227-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="ad227-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="ad227-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ad227-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ad227-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ad227-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad227-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad227-124">Parent elements</span></span>  
  
|<span data-ttu-id="ad227-125">Element</span><span class="sxs-lookup"><span data-stu-id="ad227-125">Element</span></span>|<span data-ttu-id="ad227-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad227-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad227-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad227-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ad227-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ad227-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad227-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad227-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ad227-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ad227-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad227-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ad227-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

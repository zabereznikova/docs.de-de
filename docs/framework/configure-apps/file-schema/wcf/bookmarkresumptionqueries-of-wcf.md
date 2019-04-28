---
title: <bookmarkResumptionQueries> von WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 4b11543e240b482d52c157083d1184db4f81bb04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673432"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="2ce2c-102">\<BookmarkResumptionQueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="2ce2c-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="2ce2c-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2ce2c-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="2ce2c-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2ce2c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="2ce2c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ce2c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2ce2c-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2ce2c-107">\<tracking></span></span>  
<span data-ttu-id="2ce2c-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="2ce2c-108">\<profiles></span></span>  
<span data-ttu-id="2ce2c-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ce2c-109">\<trackingProfile></span></span>  
<span data-ttu-id="2ce2c-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2ce2c-110">\<workflow></span></span>  
<span data-ttu-id="2ce2c-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="2ce2c-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2ce2c-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2ce2c-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce2c-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ce2c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce2c-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2ce2c-114">Attributes and elements</span></span>  
  
<span data-ttu-id="2ce2c-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce2c-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ce2c-116">Attributes</span></span>  
  
<span data-ttu-id="2ce2c-117">Keine</span><span class="sxs-lookup"><span data-stu-id="2ce2c-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ce2c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ce2c-118">Child elements</span></span>  
  
|<span data-ttu-id="2ce2c-119">Element</span><span class="sxs-lookup"><span data-stu-id="2ce2c-119">Element</span></span>|<span data-ttu-id="2ce2c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ce2c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce2c-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2ce2c-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="2ce2c-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2ce2c-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce2c-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ce2c-124">Parent elements</span></span>  
  
|<span data-ttu-id="2ce2c-125">Element</span><span class="sxs-lookup"><span data-stu-id="2ce2c-125">Element</span></span>|<span data-ttu-id="2ce2c-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ce2c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce2c-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2ce2c-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2ce2c-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ce2c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ce2c-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2ce2c-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2ce2c-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2ce2c-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2ce2c-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

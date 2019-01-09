---
title: '&lt;bookmarkResumptionQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: ba8c98557a859f4bd37b9aaca80a44c393429da4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146081"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="7dd31-102">&lt;bookmarkResumptionQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="7dd31-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="7dd31-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="7dd31-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7dd31-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="7dd31-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="7dd31-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7dd31-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="7dd31-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7dd31-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7dd31-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="7dd31-107">\<tracking></span></span>  
<span data-ttu-id="7dd31-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="7dd31-108">\<profiles></span></span>  
<span data-ttu-id="7dd31-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7dd31-109">\<trackingProfile></span></span>  
<span data-ttu-id="7dd31-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="7dd31-110">\<workflow></span></span>  
<span data-ttu-id="7dd31-111">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="7dd31-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="7dd31-112">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="7dd31-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd31-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dd31-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dd31-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-114">Attributes and elements</span></span>  
  
<span data-ttu-id="7dd31-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dd31-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dd31-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dd31-116">Attributes</span></span>  
  
<span data-ttu-id="7dd31-117">Keine</span><span class="sxs-lookup"><span data-stu-id="7dd31-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7dd31-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-118">Child elements</span></span>  
  
|<span data-ttu-id="7dd31-119">Element</span><span class="sxs-lookup"><span data-stu-id="7dd31-119">Element</span></span>|<span data-ttu-id="7dd31-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dd31-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dd31-121">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="7dd31-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="7dd31-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="7dd31-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7dd31-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="7dd31-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dd31-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-124">Parent elements</span></span>  
  
|<span data-ttu-id="7dd31-125">Element</span><span class="sxs-lookup"><span data-stu-id="7dd31-125">Element</span></span>|<span data-ttu-id="7dd31-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dd31-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dd31-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7dd31-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7dd31-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7dd31-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dd31-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dd31-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType> 
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="7dd31-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="7dd31-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="7dd31-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="7dd31-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

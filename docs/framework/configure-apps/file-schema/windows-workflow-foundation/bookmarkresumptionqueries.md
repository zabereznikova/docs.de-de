---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109408"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="4ddd8-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="4ddd8-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="4ddd8-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4ddd8-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="4ddd8-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4ddd8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4ddd8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4ddd8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4ddd8-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4ddd8-106">\<tracking></span></span>  
<span data-ttu-id="4ddd8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4ddd8-107">\<trackingProfile></span></span>  
<span data-ttu-id="4ddd8-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4ddd8-108">\<workflow></span></span>  
<span data-ttu-id="4ddd8-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="4ddd8-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="4ddd8-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="4ddd8-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ddd8-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ddd8-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ddd8-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ddd8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4ddd8-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ddd8-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ddd8-114">Attributes</span></span>  
 <span data-ttu-id="4ddd8-115">Keine</span><span class="sxs-lookup"><span data-stu-id="4ddd8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4ddd8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ddd8-116">Child Elements</span></span>  
  
|<span data-ttu-id="4ddd8-117">Element</span><span class="sxs-lookup"><span data-stu-id="4ddd8-117">Element</span></span>|<span data-ttu-id="4ddd8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddd8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ddd8-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="4ddd8-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="4ddd8-120">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4ddd8-121">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ddd8-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ddd8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4ddd8-123">Element</span><span class="sxs-lookup"><span data-stu-id="4ddd8-123">Element</span></span>|<span data-ttu-id="4ddd8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddd8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ddd8-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4ddd8-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4ddd8-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4ddd8-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ddd8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ddd8-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4ddd8-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="4ddd8-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4ddd8-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="4ddd8-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

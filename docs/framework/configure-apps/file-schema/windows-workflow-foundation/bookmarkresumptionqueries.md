---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: ae6a81123379ecd0e7fdc72f4e115a462f81eb90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555036"
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="00db7-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="00db7-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="00db7-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="00db7-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="00db7-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="00db7-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="00db7-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="00db7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="00db7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="00db7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="00db7-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="00db7-107">\<tracking></span></span>  
<span data-ttu-id="00db7-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="00db7-108">\<trackingProfile></span></span>  
<span data-ttu-id="00db7-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="00db7-109">\<workflow></span></span>  
<span data-ttu-id="00db7-110">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="00db7-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="00db7-111">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="00db7-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00db7-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="00db7-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00db7-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00db7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="00db7-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00db7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00db7-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="00db7-115">Attributes</span></span>  
 <span data-ttu-id="00db7-116">Keine</span><span class="sxs-lookup"><span data-stu-id="00db7-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00db7-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00db7-117">Child Elements</span></span>  
  
|<span data-ttu-id="00db7-118">Element</span><span class="sxs-lookup"><span data-stu-id="00db7-118">Element</span></span>|<span data-ttu-id="00db7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00db7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00db7-120">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="00db7-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="00db7-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="00db7-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="00db7-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="00db7-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00db7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00db7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00db7-124">Element</span><span class="sxs-lookup"><span data-stu-id="00db7-124">Element</span></span>|<span data-ttu-id="00db7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00db7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00db7-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="00db7-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="00db7-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="00db7-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00db7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00db7-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00db7-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="00db7-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00db7-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="00db7-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

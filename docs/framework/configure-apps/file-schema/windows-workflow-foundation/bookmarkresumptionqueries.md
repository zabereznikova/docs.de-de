---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: b0ce29213f1f281e8581b90dda17aba1bdc29072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="0f684-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="0f684-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="0f684-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0f684-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0f684-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0f684-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0f684-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0f684-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0f684-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0f684-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0f684-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="0f684-107">\<tracking></span></span>  
<span data-ttu-id="0f684-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0f684-108">\<trackingProfile></span></span>  
<span data-ttu-id="0f684-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="0f684-109">\<workflow></span></span>  
<span data-ttu-id="0f684-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0f684-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0f684-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0f684-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f684-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f684-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f684-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0f684-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0f684-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f684-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f684-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f684-115">Attributes</span></span>  
 <span data-ttu-id="0f684-116">Keine</span><span class="sxs-lookup"><span data-stu-id="0f684-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f684-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f684-117">Child Elements</span></span>  
  
|<span data-ttu-id="0f684-118">Element</span><span class="sxs-lookup"><span data-stu-id="0f684-118">Element</span></span>|<span data-ttu-id="0f684-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f684-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f684-120">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0f684-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="0f684-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0f684-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0f684-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0f684-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f684-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f684-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0f684-124">Element</span><span class="sxs-lookup"><span data-stu-id="0f684-124">Element</span></span>|<span data-ttu-id="0f684-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f684-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f684-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="0f684-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0f684-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0f684-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f684-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f684-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0f684-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0f684-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0f684-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0f684-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

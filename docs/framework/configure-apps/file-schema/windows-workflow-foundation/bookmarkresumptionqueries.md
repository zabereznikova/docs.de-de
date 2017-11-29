---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bf209525bcc9748e9a5f5b71a0407a4eca1a897
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="8ba4d-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8ba4d-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="8ba4d-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8ba4d-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="8ba4d-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8ba4d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8ba4d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8ba4d-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-107">\<tracking></span></span>  
<span data-ttu-id="8ba4d-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-108">\<trackingProfile></span></span>  
<span data-ttu-id="8ba4d-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-109">\<workflow></span></span>  
<span data-ttu-id="8ba4d-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="8ba4d-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba4d-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ba4d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ba4d-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8ba4d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8ba4d-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ba4d-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="8ba4d-115">Attributes</span></span>  
 <span data-ttu-id="8ba4d-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ba4d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ba4d-117">Child Elements</span></span>  
  
|<span data-ttu-id="8ba4d-118">Element</span><span class="sxs-lookup"><span data-stu-id="8ba4d-118">Element</span></span>|<span data-ttu-id="8ba4d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ba4d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ba4d-120">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="8ba4d-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8ba4d-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ba4d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ba4d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8ba4d-124">Element</span><span class="sxs-lookup"><span data-stu-id="8ba4d-124">Element</span></span>|<span data-ttu-id="8ba4d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ba4d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ba4d-126">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="8ba4d-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8ba4d-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8ba4d-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ba4d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ba4d-128">See Also</span></span>  
 <span data-ttu-id="8ba4d-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8ba4d-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="8ba4d-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8ba4d-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="8ba4d-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8ba4d-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8ba4d-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8ba4d-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

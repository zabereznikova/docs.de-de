---
title: '&lt;bookmarkResumptionQueries&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c29f4c0cd92b2c4e8263e1893e7deefc2f14624a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="beeb9-102">&lt;bookmarkResumptionQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="beeb9-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="beeb9-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="beeb9-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="beeb9-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="beeb9-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="beeb9-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="beeb9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="beeb9-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="beeb9-106">\<system.serviceModel></span></span>  
<span data-ttu-id="beeb9-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="beeb9-107">\<tracking></span></span>  
<span data-ttu-id="beeb9-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="beeb9-108">\<trackingProfile></span></span>  
<span data-ttu-id="beeb9-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="beeb9-109">\<workflow></span></span>  
<span data-ttu-id="beeb9-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="beeb9-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="beeb9-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="beeb9-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beeb9-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="beeb9-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="beeb9-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="beeb9-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="beeb9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beeb9-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="beeb9-115">Attributes</span></span>  
 <span data-ttu-id="beeb9-116">Keine</span><span class="sxs-lookup"><span data-stu-id="beeb9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="beeb9-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb9-117">Child Elements</span></span>  
  
|<span data-ttu-id="beeb9-118">Element</span><span class="sxs-lookup"><span data-stu-id="beeb9-118">Element</span></span>|<span data-ttu-id="beeb9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beeb9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beeb9-120">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="beeb9-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="beeb9-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="beeb9-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="beeb9-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="beeb9-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="beeb9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beeb9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="beeb9-124">Element</span><span class="sxs-lookup"><span data-stu-id="beeb9-124">Element</span></span>|<span data-ttu-id="beeb9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beeb9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beeb9-126">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="beeb9-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="beeb9-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="beeb9-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="beeb9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beeb9-128">See Also</span></span>  
 <span data-ttu-id="beeb9-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="beeb9-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="beeb9-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="beeb9-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="beeb9-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="beeb9-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="beeb9-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="beeb9-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

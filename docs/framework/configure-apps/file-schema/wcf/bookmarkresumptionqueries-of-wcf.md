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
ms.openlocfilehash: aa46d62262b91d5b88564b50f97fccf7aefefa6d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="b0bbf-102">&lt;bookmarkResumptionQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="b0bbf-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="b0bbf-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b0bbf-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="b0bbf-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b0bbf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="b0bbf-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b0bbf-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-107">\<tracking></span></span>  
<span data-ttu-id="b0bbf-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-108">\<trackingProfile></span></span>  
<span data-ttu-id="b0bbf-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-109">\<workflow></span></span>  
<span data-ttu-id="b0bbf-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="b0bbf-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bbf-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0bbf-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b0bbf-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0bbf-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b0bbf-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0bbf-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0bbf-115">Attributes</span></span>  
 <span data-ttu-id="b0bbf-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0bbf-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0bbf-117">Child Elements</span></span>  
  
|<span data-ttu-id="b0bbf-118">Element</span><span class="sxs-lookup"><span data-stu-id="b0bbf-118">Element</span></span>|<span data-ttu-id="b0bbf-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0bbf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0bbf-120">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="b0bbf-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b0bbf-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0bbf-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0bbf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b0bbf-124">Element</span><span class="sxs-lookup"><span data-stu-id="b0bbf-124">Element</span></span>|<span data-ttu-id="b0bbf-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0bbf-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0bbf-126">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b0bbf-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b0bbf-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b0bbf-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0bbf-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0bbf-128">See Also</span></span>  
 <span data-ttu-id="b0bbf-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b0bbf-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b0bbf-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b0bbf-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b0bbf-131">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b0bbf-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b0bbf-132">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b0bbf-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

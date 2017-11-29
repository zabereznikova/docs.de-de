---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e52b4ef5104397d3c4b8abc89a1d637b17fcde9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="1e2aa-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="1e2aa-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="1e2aa-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="1e2aa-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1e2aa-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="1e2aa-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="1e2aa-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1e2aa-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1e2aa-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1e2aa-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-107">\<tracking></span></span>  
<span data-ttu-id="1e2aa-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-108">\<trackingProfile></span></span>  
<span data-ttu-id="1e2aa-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-109">\<workflow></span></span>  
<span data-ttu-id="1e2aa-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1e2aa-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e2aa-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e2aa-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e2aa-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e2aa-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1e2aa-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e2aa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e2aa-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e2aa-115">Attributes</span></span>  
  
|<span data-ttu-id="1e2aa-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="1e2aa-116">Attribute</span></span>|<span data-ttu-id="1e2aa-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e2aa-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e2aa-118">Name</span><span class="sxs-lookup"><span data-stu-id="1e2aa-118">name</span></span>|<span data-ttu-id="1e2aa-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="1e2aa-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e2aa-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e2aa-120">Child Elements</span></span>  
 <span data-ttu-id="1e2aa-121">Keine</span><span class="sxs-lookup"><span data-stu-id="1e2aa-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e2aa-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e2aa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1e2aa-123">Element</span><span class="sxs-lookup"><span data-stu-id="1e2aa-123">Element</span></span>|<span data-ttu-id="1e2aa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e2aa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e2aa-125">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="1e2aa-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="1e2aa-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="1e2aa-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e2aa-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e2aa-127">See Also</span></span>  
 <span data-ttu-id="1e2aa-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1e2aa-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1e2aa-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1e2aa-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1e2aa-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="1e2aa-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1e2aa-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="1e2aa-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

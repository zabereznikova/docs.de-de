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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bafb044d052692385e0be0f4dbb1271eca847b1a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="984dc-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="984dc-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="984dc-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="984dc-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="984dc-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="984dc-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="984dc-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="984dc-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="984dc-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="984dc-106">\<system.serviceModel></span></span>  
<span data-ttu-id="984dc-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="984dc-107">\<tracking></span></span>  
<span data-ttu-id="984dc-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="984dc-108">\<trackingProfile></span></span>  
<span data-ttu-id="984dc-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="984dc-109">\<workflow></span></span>  
<span data-ttu-id="984dc-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="984dc-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="984dc-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="984dc-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="984dc-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="984dc-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="984dc-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="984dc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="984dc-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="984dc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="984dc-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="984dc-115">Attributes</span></span>  
  
|<span data-ttu-id="984dc-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="984dc-116">Attribute</span></span>|<span data-ttu-id="984dc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="984dc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="984dc-118">Name</span><span class="sxs-lookup"><span data-stu-id="984dc-118">name</span></span>|<span data-ttu-id="984dc-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="984dc-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="984dc-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="984dc-120">Child Elements</span></span>  
 <span data-ttu-id="984dc-121">Keine</span><span class="sxs-lookup"><span data-stu-id="984dc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="984dc-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="984dc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="984dc-123">Element</span><span class="sxs-lookup"><span data-stu-id="984dc-123">Element</span></span>|<span data-ttu-id="984dc-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="984dc-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="984dc-125">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="984dc-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="984dc-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="984dc-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="984dc-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="984dc-127">See Also</span></span>  
 <span data-ttu-id="984dc-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="984dc-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="984dc-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="984dc-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="984dc-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="984dc-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="984dc-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="984dc-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

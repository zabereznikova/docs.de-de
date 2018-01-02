---
title: '&lt;bookmarkResumptionQuery&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3240fcf026869aee7540c0e792ccd81e2592e620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="f1681-102">&lt;bookmarkResumptionQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="f1681-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="f1681-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="f1681-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f1681-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f1681-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="f1681-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f1681-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f1681-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f1681-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f1681-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="f1681-107">\<tracking></span></span>  
<span data-ttu-id="f1681-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f1681-108">\<trackingProfile></span></span>  
<span data-ttu-id="f1681-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="f1681-109">\<workflow></span></span>  
<span data-ttu-id="f1681-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="f1681-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="f1681-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="f1681-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1681-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1681-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1681-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f1681-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f1681-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1681-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1681-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="f1681-115">Attributes</span></span>  
  
|<span data-ttu-id="f1681-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="f1681-116">Attribute</span></span>|<span data-ttu-id="f1681-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1681-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1681-118">Name</span><span class="sxs-lookup"><span data-stu-id="f1681-118">name</span></span>|<span data-ttu-id="f1681-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="f1681-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1681-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1681-120">Child Elements</span></span>  
 <span data-ttu-id="f1681-121">Keine</span><span class="sxs-lookup"><span data-stu-id="f1681-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1681-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1681-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f1681-123">Element</span><span class="sxs-lookup"><span data-stu-id="f1681-123">Element</span></span>|<span data-ttu-id="f1681-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1681-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1681-125">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="f1681-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="f1681-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f1681-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1681-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1681-127">See Also</span></span>  
 <span data-ttu-id="f1681-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f1681-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f1681-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f1681-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f1681-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f1681-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f1681-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f1681-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

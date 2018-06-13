---
title: '&lt;bookmarkResumptionQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 083b42efdd2b10dad870b6590fc20331a090f8aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748255"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="cd61e-102">&lt;bookmarkResumptionQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="cd61e-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="cd61e-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="cd61e-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="cd61e-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="cd61e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="cd61e-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cd61e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="cd61e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cd61e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cd61e-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="cd61e-107">\<tracking></span></span>  
<span data-ttu-id="cd61e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cd61e-108">\<trackingProfile></span></span>  
<span data-ttu-id="cd61e-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="cd61e-109">\<workflow></span></span>  
<span data-ttu-id="cd61e-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="cd61e-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="cd61e-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="cd61e-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd61e-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd61e-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cd61e-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd61e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cd61e-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd61e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd61e-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd61e-115">Attributes</span></span>  
  
|<span data-ttu-id="cd61e-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd61e-116">Attribute</span></span>|<span data-ttu-id="cd61e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd61e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd61e-118">Name</span><span class="sxs-lookup"><span data-stu-id="cd61e-118">name</span></span>|<span data-ttu-id="cd61e-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="cd61e-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd61e-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd61e-120">Child Elements</span></span>  
 <span data-ttu-id="cd61e-121">Keine</span><span class="sxs-lookup"><span data-stu-id="cd61e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd61e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd61e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cd61e-123">Element</span><span class="sxs-lookup"><span data-stu-id="cd61e-123">Element</span></span>|<span data-ttu-id="cd61e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd61e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd61e-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="cd61e-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="cd61e-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="cd61e-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd61e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd61e-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="cd61e-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="cd61e-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cd61e-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="cd61e-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

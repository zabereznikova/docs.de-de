---
title: '&lt;bookmarkResumptionQueries&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 8a83f521e444838b6495221c00211710dd99ab6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753039"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="d8231-102">&lt;bookmarkResumptionQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="d8231-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="d8231-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d8231-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d8231-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d8231-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="d8231-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d8231-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="d8231-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d8231-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d8231-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="d8231-107">\<tracking></span></span>  
<span data-ttu-id="d8231-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d8231-108">\<trackingProfile></span></span>  
<span data-ttu-id="d8231-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="d8231-109">\<workflow></span></span>  
<span data-ttu-id="d8231-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="d8231-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="d8231-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="d8231-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8231-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8231-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d8231-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8231-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d8231-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8231-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8231-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8231-115">Attributes</span></span>  
 <span data-ttu-id="d8231-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d8231-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8231-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8231-117">Child Elements</span></span>  
  
|<span data-ttu-id="d8231-118">Element</span><span class="sxs-lookup"><span data-stu-id="d8231-118">Element</span></span>|<span data-ttu-id="d8231-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8231-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8231-120">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="d8231-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="d8231-121">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d8231-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d8231-122">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="d8231-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8231-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8231-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d8231-124">Element</span><span class="sxs-lookup"><span data-stu-id="d8231-124">Element</span></span>|<span data-ttu-id="d8231-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8231-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8231-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d8231-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d8231-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d8231-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8231-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8231-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="d8231-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="d8231-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d8231-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="d8231-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

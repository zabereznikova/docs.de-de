---
title: '&lt;bookmarkResumptionQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 6463404e17edff8eb1efe3f96e44b5b9997ffca3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147810"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="34f2e-102">&lt;bookmarkResumptionQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="34f2e-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="34f2e-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="34f2e-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="34f2e-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="34f2e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="34f2e-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="34f2e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="34f2e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="34f2e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="34f2e-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="34f2e-107">\<tracking></span></span>  
<span data-ttu-id="34f2e-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="34f2e-108">\<profiles></span></span>  
<span data-ttu-id="34f2e-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="34f2e-109">\<trackingProfile></span></span>  
<span data-ttu-id="34f2e-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="34f2e-110">\<workflow></span></span>  
<span data-ttu-id="34f2e-111">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="34f2e-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="34f2e-112">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="34f2e-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f2e-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="34f2e-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34f2e-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34f2e-114">Attributes and elements</span></span>

<span data-ttu-id="34f2e-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34f2e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34f2e-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="34f2e-116">Attributes</span></span>  
  
|<span data-ttu-id="34f2e-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="34f2e-117">Attribute</span></span>|<span data-ttu-id="34f2e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34f2e-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="34f2e-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="34f2e-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34f2e-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34f2e-120">Child elements</span></span>

<span data-ttu-id="34f2e-121">Keine</span><span class="sxs-lookup"><span data-stu-id="34f2e-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="34f2e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34f2e-122">Parent elements</span></span>  
  
|<span data-ttu-id="34f2e-123">Element</span><span class="sxs-lookup"><span data-stu-id="34f2e-123">Element</span></span>|<span data-ttu-id="34f2e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34f2e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34f2e-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="34f2e-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="34f2e-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="34f2e-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34f2e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34f2e-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="34f2e-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="34f2e-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="34f2e-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="34f2e-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

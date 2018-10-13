---
title: '&lt;bookmarkResumptionQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: f0721e7e14d543b1ff212fe59ed6a2de0a8a9968
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308416"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="526c0-102">&lt;bookmarkResumptionQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="526c0-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="526c0-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="526c0-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="526c0-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="526c0-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="526c0-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="526c0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="526c0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="526c0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="526c0-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="526c0-107">\<tracking></span></span>  
<span data-ttu-id="526c0-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="526c0-108">\<profiles></span></span>  
<span data-ttu-id="526c0-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="526c0-109">\<trackingProfile></span></span>  
<span data-ttu-id="526c0-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="526c0-110">\<workflow></span></span>  
<span data-ttu-id="526c0-111">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="526c0-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="526c0-112">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="526c0-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526c0-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="526c0-113">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="526c0-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="526c0-114">Attributes and elements</span></span>

<span data-ttu-id="526c0-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="526c0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="526c0-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="526c0-116">Attributes</span></span>  
  
|<span data-ttu-id="526c0-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="526c0-117">Attribute</span></span>|<span data-ttu-id="526c0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="526c0-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="526c0-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="526c0-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="526c0-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="526c0-120">Child elements</span></span>

<span data-ttu-id="526c0-121">Keine</span><span class="sxs-lookup"><span data-stu-id="526c0-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="526c0-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="526c0-122">Parent elements</span></span>  
  
|<span data-ttu-id="526c0-123">Element</span><span class="sxs-lookup"><span data-stu-id="526c0-123">Element</span></span>|<span data-ttu-id="526c0-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="526c0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="526c0-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="526c0-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="526c0-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="526c0-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="526c0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="526c0-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="526c0-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="526c0-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="526c0-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="526c0-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

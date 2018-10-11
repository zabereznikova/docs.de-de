---
title: '&lt;bookmarkResumptionQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 07215347da19a05d5915296668d990853fdae646
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087790"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="2ccc3-102">&lt;bookmarkResumptionQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="2ccc3-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="2ccc3-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="2ccc3-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2ccc3-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="2ccc3-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="2ccc3-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2ccc3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="2ccc3-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ccc3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2ccc3-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="2ccc3-107">\<tracking></span></span>  
<span data-ttu-id="2ccc3-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ccc3-108">\<trackingProfile></span></span>  
<span data-ttu-id="2ccc3-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="2ccc3-109">\<workflow></span></span>  
<span data-ttu-id="2ccc3-110">\<BookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2ccc3-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2ccc3-111">\<BookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="2ccc3-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccc3-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ccc3-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="2ccc3-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2ccc3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2ccc3-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ccc3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ccc3-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ccc3-115">Attributes</span></span>  
  
|<span data-ttu-id="2ccc3-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="2ccc3-116">Attribute</span></span>|<span data-ttu-id="2ccc3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ccc3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ccc3-118">Name</span><span class="sxs-lookup"><span data-stu-id="2ccc3-118">name</span></span>|<span data-ttu-id="2ccc3-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="2ccc3-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ccc3-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ccc3-120">Child Elements</span></span>  
 <span data-ttu-id="2ccc3-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2ccc3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ccc3-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ccc3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2ccc3-123">Element</span><span class="sxs-lookup"><span data-stu-id="2ccc3-123">Element</span></span>|<span data-ttu-id="2ccc3-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ccc3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ccc3-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="2ccc3-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="2ccc3-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2ccc3-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ccc3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ccc3-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="2ccc3-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="2ccc3-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2ccc3-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="2ccc3-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

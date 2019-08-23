---
title: <bookmarkResumptionQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: ee8457645a0b54e21ef27c2891ebea97d6cc547b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926359"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="a4feb-102">\<BookmarkResumptionQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="a4feb-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="a4feb-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4feb-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a4feb-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a4feb-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="a4feb-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a4feb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="a4feb-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a4feb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a4feb-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="a4feb-107">\<tracking></span></span>  
<span data-ttu-id="a4feb-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="a4feb-108">\<profiles></span></span>  
<span data-ttu-id="a4feb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a4feb-109">\<trackingProfile></span></span>  
<span data-ttu-id="a4feb-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a4feb-110">\<workflow></span></span>  
<span data-ttu-id="a4feb-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a4feb-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="a4feb-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a4feb-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4feb-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4feb-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4feb-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4feb-114">Attributes and elements</span></span>

<span data-ttu-id="a4feb-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4feb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4feb-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4feb-116">Attributes</span></span>  
  
|<span data-ttu-id="a4feb-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4feb-117">Attribute</span></span>|<span data-ttu-id="a4feb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4feb-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="a4feb-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="a4feb-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4feb-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4feb-120">Child elements</span></span>

<span data-ttu-id="a4feb-121">Keine</span><span class="sxs-lookup"><span data-stu-id="a4feb-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="a4feb-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4feb-122">Parent elements</span></span>  
  
|<span data-ttu-id="a4feb-123">Element</span><span class="sxs-lookup"><span data-stu-id="a4feb-123">Element</span></span>|<span data-ttu-id="a4feb-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4feb-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4feb-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a4feb-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="a4feb-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4feb-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4feb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4feb-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a4feb-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a4feb-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a4feb-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a4feb-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

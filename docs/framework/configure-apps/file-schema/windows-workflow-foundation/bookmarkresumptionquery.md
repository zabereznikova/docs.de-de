---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: a5eb00d1e094484e3ec01e0db18719ec50e4b953
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515067"
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="6c264-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6c264-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="6c264-103">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="6c264-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="6c264-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="6c264-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="6c264-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6c264-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6c264-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c264-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6c264-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6c264-107">\<tracking></span></span>  
<span data-ttu-id="6c264-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6c264-108">\<trackingProfile></span></span>  
<span data-ttu-id="6c264-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6c264-109">\<workflow></span></span>  
<span data-ttu-id="6c264-110">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="6c264-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="6c264-111">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="6c264-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c264-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c264-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c264-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6c264-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c264-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c264-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c264-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="6c264-115">Attributes</span></span>  
  
|<span data-ttu-id="6c264-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="6c264-116">Attribute</span></span>|<span data-ttu-id="6c264-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c264-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c264-118">Name</span><span class="sxs-lookup"><span data-stu-id="6c264-118">name</span></span>|<span data-ttu-id="6c264-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="6c264-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c264-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c264-120">Child Elements</span></span>  
 <span data-ttu-id="6c264-121">Keine</span><span class="sxs-lookup"><span data-stu-id="6c264-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c264-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6c264-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6c264-123">Element</span><span class="sxs-lookup"><span data-stu-id="6c264-123">Element</span></span>|<span data-ttu-id="6c264-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c264-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c264-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="6c264-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="6c264-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="6c264-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c264-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c264-127">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c264-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="6c264-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c264-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="6c264-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

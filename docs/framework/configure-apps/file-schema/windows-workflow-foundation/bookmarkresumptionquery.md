---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 7fb298bcbc5b4bf5d699d3c79936ca3c15f67c0e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268183"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="51098-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="51098-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="51098-102">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="51098-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="51098-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="51098-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="51098-104">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="51098-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="51098-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="51098-105">\<system.serviceModel></span></span>  
<span data-ttu-id="51098-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="51098-106">\<tracking></span></span>  
<span data-ttu-id="51098-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="51098-107">\<trackingProfile></span></span>  
<span data-ttu-id="51098-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="51098-108">\<workflow></span></span>  
<span data-ttu-id="51098-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="51098-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="51098-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="51098-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51098-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="51098-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51098-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="51098-112">Attributes and Elements</span></span>  
 <span data-ttu-id="51098-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="51098-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51098-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="51098-114">Attributes</span></span>  
  
|<span data-ttu-id="51098-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="51098-115">Attribute</span></span>|<span data-ttu-id="51098-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51098-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51098-117">Name</span><span class="sxs-lookup"><span data-stu-id="51098-117">name</span></span>|<span data-ttu-id="51098-118">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="51098-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51098-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51098-119">Child Elements</span></span>  
 <span data-ttu-id="51098-120">Keine</span><span class="sxs-lookup"><span data-stu-id="51098-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51098-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="51098-121">Parent Elements</span></span>  
  
|<span data-ttu-id="51098-122">Element</span><span class="sxs-lookup"><span data-stu-id="51098-122">Element</span></span>|<span data-ttu-id="51098-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51098-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51098-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="51098-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="51098-125">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="51098-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51098-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51098-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="51098-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="51098-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="51098-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="51098-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

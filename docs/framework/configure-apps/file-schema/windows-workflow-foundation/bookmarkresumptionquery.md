---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945962"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="0bfd2-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="0bfd2-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="0bfd2-102">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="0bfd2-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0bfd2-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0bfd2-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0bfd2-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0bfd2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0bfd2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0bfd2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0bfd2-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="0bfd2-106">\<tracking></span></span>  
<span data-ttu-id="0bfd2-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0bfd2-107">\<trackingProfile></span></span>  
<span data-ttu-id="0bfd2-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="0bfd2-108">\<workflow></span></span>  
<span data-ttu-id="0bfd2-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="0bfd2-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0bfd2-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="0bfd2-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bfd2-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bfd2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bfd2-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0bfd2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0bfd2-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0bfd2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bfd2-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="0bfd2-114">Attributes</span></span>  
  
|<span data-ttu-id="0bfd2-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="0bfd2-115">Attribute</span></span>|<span data-ttu-id="0bfd2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bfd2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bfd2-117">Name</span><span class="sxs-lookup"><span data-stu-id="0bfd2-117">name</span></span>|<span data-ttu-id="0bfd2-118">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="0bfd2-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bfd2-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bfd2-119">Child Elements</span></span>  
 <span data-ttu-id="0bfd2-120">Keine</span><span class="sxs-lookup"><span data-stu-id="0bfd2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bfd2-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bfd2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0bfd2-122">Element</span><span class="sxs-lookup"><span data-stu-id="0bfd2-122">Element</span></span>|<span data-ttu-id="0bfd2-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bfd2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bfd2-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="0bfd2-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="0bfd2-125">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0bfd2-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bfd2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bfd2-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0bfd2-127">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0bfd2-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0bfd2-128">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0bfd2-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

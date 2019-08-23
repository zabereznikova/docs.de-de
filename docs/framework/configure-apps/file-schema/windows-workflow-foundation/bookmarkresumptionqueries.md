---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945988"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="0b1b6-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="0b1b6-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="0b1b6-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0b1b6-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0b1b6-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1b6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0b1b6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b1b6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0b1b6-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="0b1b6-106">\<tracking></span></span>  
<span data-ttu-id="0b1b6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0b1b6-107">\<trackingProfile></span></span>  
<span data-ttu-id="0b1b6-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="0b1b6-108">\<workflow></span></span>  
<span data-ttu-id="0b1b6-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="0b1b6-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0b1b6-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="0b1b6-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1b6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b1b6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b1b6-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b1b6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0b1b6-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b1b6-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b1b6-114">Attributes</span></span>  
 <span data-ttu-id="0b1b6-115">Keine</span><span class="sxs-lookup"><span data-stu-id="0b1b6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b1b6-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b1b6-116">Child Elements</span></span>  
  
|<span data-ttu-id="0b1b6-117">Element</span><span class="sxs-lookup"><span data-stu-id="0b1b6-117">Element</span></span>|<span data-ttu-id="0b1b6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b1b6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b1b6-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="0b1b6-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="0b1b6-120">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0b1b6-121">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b1b6-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b1b6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0b1b6-123">Element</span><span class="sxs-lookup"><span data-stu-id="0b1b6-123">Element</span></span>|<span data-ttu-id="0b1b6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b1b6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b1b6-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="0b1b6-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="0b1b6-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b1b6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b1b6-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0b1b6-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0b1b6-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0b1b6-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0b1b6-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

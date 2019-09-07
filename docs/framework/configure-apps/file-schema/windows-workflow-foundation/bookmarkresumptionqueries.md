---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398864"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="af76f-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="af76f-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="af76f-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="af76f-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="af76f-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="af76f-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="af76f-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="af76f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="af76f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af76f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af76f-106">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="af76f-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="af76f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="af76f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="af76f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="af76f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="af76f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="af76f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="af76f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkresumptionqueries >**</span><span class="sxs-lookup"><span data-stu-id="af76f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="af76f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="af76f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af76f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af76f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="af76f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af76f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af76f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="af76f-114">Attributes</span></span>  
 <span data-ttu-id="af76f-115">Keine</span><span class="sxs-lookup"><span data-stu-id="af76f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af76f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af76f-116">Child Elements</span></span>  
  
|<span data-ttu-id="af76f-117">Element</span><span class="sxs-lookup"><span data-stu-id="af76f-117">Element</span></span>|<span data-ttu-id="af76f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af76f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af76f-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="af76f-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="af76f-120">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="af76f-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="af76f-121">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="af76f-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af76f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af76f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="af76f-123">Element</span><span class="sxs-lookup"><span data-stu-id="af76f-123">Element</span></span>|<span data-ttu-id="af76f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af76f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af76f-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="af76f-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="af76f-126">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die **activityDefinitionId** -Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="af76f-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af76f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af76f-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="af76f-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="af76f-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="af76f-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="af76f-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398850"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="bf516-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="bf516-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="bf516-102">Stellt eine Abfrage dar, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="bf516-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="bf516-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="bf516-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="bf516-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="bf516-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bf516-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf516-106">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="bf516-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="bf516-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="bf516-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="bf516-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkresumptionqueries >** ](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="bf516-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="bf516-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<BookmarkResumptionQuery->**</span><span class="sxs-lookup"><span data-stu-id="bf516-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf516-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf516-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf516-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf516-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bf516-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf516-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf516-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf516-115">Attributes</span></span>  
  
|<span data-ttu-id="bf516-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="bf516-116">Attribute</span></span>|<span data-ttu-id="bf516-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf516-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf516-118">Name</span><span class="sxs-lookup"><span data-stu-id="bf516-118">name</span></span>|<span data-ttu-id="bf516-119">Eine Zeichenfolge, die den Namen des zu abonnierenden Lesezeichendatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="bf516-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf516-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf516-120">Child Elements</span></span>  
 <span data-ttu-id="bf516-121">Keine</span><span class="sxs-lookup"><span data-stu-id="bf516-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf516-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf516-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bf516-123">Element</span><span class="sxs-lookup"><span data-stu-id="bf516-123">Element</span></span>|<span data-ttu-id="bf516-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf516-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf516-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="bf516-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="bf516-126">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="bf516-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf516-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf516-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bf516-128">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="bf516-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bf516-129">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="bf516-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

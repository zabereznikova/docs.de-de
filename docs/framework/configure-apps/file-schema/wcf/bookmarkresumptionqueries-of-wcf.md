---
title: <bookmarkResumptionQueries>von WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850129"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="f490d-102">\<bookmarkresumptionqueries > von WCF</span><span class="sxs-lookup"><span data-stu-id="f490d-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="f490d-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f490d-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f490d-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f490d-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="f490d-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f490d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="f490d-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f490d-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f490d-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f490d-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f490d-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f490d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f490d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="f490d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f490d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f490d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f490d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f490d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f490d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkresumptionqueries >**</span><span class="sxs-lookup"><span data-stu-id="f490d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f490d-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="f490d-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f490d-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f490d-114">Attributes and elements</span></span>  
  
<span data-ttu-id="f490d-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f490d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f490d-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="f490d-116">Attributes</span></span>  
  
<span data-ttu-id="f490d-117">Keine</span><span class="sxs-lookup"><span data-stu-id="f490d-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f490d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f490d-118">Child elements</span></span>  
  
|<span data-ttu-id="f490d-119">Element</span><span class="sxs-lookup"><span data-stu-id="f490d-119">Element</span></span>|<span data-ttu-id="f490d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f490d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f490d-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="f490d-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="f490d-122">Eine Abfrage, die verwendet wird, um die Wiederaufnahme eines Lesezeichens innerhalb einer Workflowinstanz nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f490d-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f490d-123">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensätze mit Lesezeichenwiederaufnahmen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="f490d-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f490d-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f490d-124">Parent elements</span></span>  
  
|<span data-ttu-id="f490d-125">Element</span><span class="sxs-lookup"><span data-stu-id="f490d-125">Element</span></span>|<span data-ttu-id="f490d-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f490d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f490d-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f490d-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="f490d-128">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f490d-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f490d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f490d-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f490d-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="f490d-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f490d-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="f490d-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

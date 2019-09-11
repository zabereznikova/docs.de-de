---
title: <activityScheduledQueries>von WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850491"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="53435-102">\<activityscheduledqueries-> von WCF</span><span class="sxs-lookup"><span data-stu-id="53435-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="53435-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="53435-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="53435-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="53435-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="53435-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="53435-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="53435-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53435-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53435-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="53435-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="53435-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="53435-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="53435-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="53435-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="53435-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="53435-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="53435-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="53435-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="53435-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityscheduledqueries->**</span><span class="sxs-lookup"><span data-stu-id="53435-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53435-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="53435-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53435-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53435-114">Attributes and elements</span></span>  

<span data-ttu-id="53435-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53435-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53435-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="53435-116">Attributes</span></span>  

<span data-ttu-id="53435-117">Keine</span><span class="sxs-lookup"><span data-stu-id="53435-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53435-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53435-118">Child elements</span></span>  
  
|<span data-ttu-id="53435-119">Element</span><span class="sxs-lookup"><span data-stu-id="53435-119">Element</span></span>|<span data-ttu-id="53435-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53435-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53435-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="53435-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="53435-122">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="53435-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53435-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53435-123">Parent elements</span></span>  
  
|<span data-ttu-id="53435-124">Element</span><span class="sxs-lookup"><span data-stu-id="53435-124">Element</span></span>|<span data-ttu-id="53435-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53435-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53435-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="53435-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="53435-127">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="53435-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53435-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53435-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="53435-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="53435-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="53435-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="53435-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

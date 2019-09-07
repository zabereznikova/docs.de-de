---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: aa6ee435c66303b5089b459ecc4ed3023297636d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398969"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="0f249-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0f249-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="0f249-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="0f249-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="0f249-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="0f249-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="0f249-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0f249-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0f249-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f249-106">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0f249-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0f249-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0f249-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0f249-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityscheduledqueries->** ](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="0f249-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="0f249-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ActivityScheduledQuery->**</span><span class="sxs-lookup"><span data-stu-id="0f249-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f249-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f249-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f249-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0f249-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0f249-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f249-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f249-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f249-115">Attributes</span></span>  
  
|<span data-ttu-id="0f249-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="0f249-116">Attribute</span></span>|<span data-ttu-id="0f249-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f249-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f249-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0f249-118">activityName</span></span>|<span data-ttu-id="0f249-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="0f249-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0f249-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0f249-120">childActivityName</span></span>|<span data-ttu-id="0f249-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f249-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f249-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f249-122">Child Elements</span></span>  
 <span data-ttu-id="0f249-123">Keine</span><span class="sxs-lookup"><span data-stu-id="0f249-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f249-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f249-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0f249-125">Element</span><span class="sxs-lookup"><span data-stu-id="0f249-125">Element</span></span>|<span data-ttu-id="0f249-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f249-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f249-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0f249-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="0f249-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="0f249-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f249-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f249-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0f249-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="0f249-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0f249-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="0f249-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

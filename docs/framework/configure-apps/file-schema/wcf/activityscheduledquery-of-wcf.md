---
title: <activityScheduledQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850465"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="da5e4-102">\<ActivityScheduledQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="da5e4-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="da5e4-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="da5e4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="da5e4-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="da5e4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="da5e4-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="da5e4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="da5e4-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da5e4-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="da5e4-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Überwachungs >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="da5e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Profile >** </span><span class="sxs-lookup"><span data-stu-id="da5e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="da5e4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<TrackingProfile->** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="da5e4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflow >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="da5e4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityscheduledqueries->** ](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="da5e4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="da5e4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ActivityScheduledQuery->**</span><span class="sxs-lookup"><span data-stu-id="da5e4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da5e4-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="da5e4-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da5e4-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da5e4-115">Attributes and elements</span></span>  

<span data-ttu-id="da5e4-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da5e4-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da5e4-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="da5e4-117">Attributes</span></span>  
  
|<span data-ttu-id="da5e4-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="da5e4-118">Attribute</span></span>|<span data-ttu-id="da5e4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5e4-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="da5e4-120">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="da5e4-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="da5e4-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="da5e4-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da5e4-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da5e4-122">Child elements</span></span>

<span data-ttu-id="da5e4-123">Keine</span><span class="sxs-lookup"><span data-stu-id="da5e4-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="da5e4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da5e4-124">Parent elements</span></span>  
  
|<span data-ttu-id="da5e4-125">Element</span><span class="sxs-lookup"><span data-stu-id="da5e4-125">Element</span></span>|<span data-ttu-id="da5e4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5e4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da5e4-127">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="da5e4-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="da5e4-128">Eine Auflistung von Abfragen, die verwendet werden, um eine Aktivität zu verfolgen, die für die Ausführung durch eine übergeordnete Aktivität geplant ist.</span><span class="sxs-lookup"><span data-stu-id="da5e4-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da5e4-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da5e4-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="da5e4-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="da5e4-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="da5e4-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="da5e4-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

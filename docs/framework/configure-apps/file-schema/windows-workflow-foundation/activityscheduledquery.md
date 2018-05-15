---
title: '&lt;activityScheduledQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 0822d0ce7dd82ff396596a0ed2431a5f2084ad8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="40b02-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="40b02-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="40b02-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="40b02-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="40b02-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="40b02-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="40b02-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="40b02-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="40b02-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="40b02-106">\<system.serviceModel></span></span>  
<span data-ttu-id="40b02-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="40b02-107">\<tracking></span></span>  
<span data-ttu-id="40b02-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="40b02-108">\<trackingProfile></span></span>  
<span data-ttu-id="40b02-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="40b02-109">\<workflow></span></span>  
<span data-ttu-id="40b02-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="40b02-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="40b02-111">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="40b02-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b02-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="40b02-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40b02-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="40b02-113">Attributes and Elements</span></span>  
 <span data-ttu-id="40b02-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40b02-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40b02-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="40b02-115">Attributes</span></span>  
  
|<span data-ttu-id="40b02-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="40b02-116">Attribute</span></span>|<span data-ttu-id="40b02-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40b02-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40b02-118">activityName</span><span class="sxs-lookup"><span data-stu-id="40b02-118">activityName</span></span>|<span data-ttu-id="40b02-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="40b02-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="40b02-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="40b02-120">childActivityName</span></span>|<span data-ttu-id="40b02-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="40b02-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40b02-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40b02-122">Child Elements</span></span>  
 <span data-ttu-id="40b02-123">Keine</span><span class="sxs-lookup"><span data-stu-id="40b02-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40b02-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40b02-124">Parent Elements</span></span>  
  
|<span data-ttu-id="40b02-125">Element</span><span class="sxs-lookup"><span data-stu-id="40b02-125">Element</span></span>|<span data-ttu-id="40b02-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40b02-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40b02-127">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="40b02-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="40b02-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="40b02-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40b02-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40b02-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="40b02-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="40b02-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="40b02-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="40b02-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

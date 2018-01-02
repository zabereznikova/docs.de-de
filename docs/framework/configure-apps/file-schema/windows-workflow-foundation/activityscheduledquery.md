---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51db0762c10459d67929867a0fe44908dc7ec750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="8d199-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="8d199-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="8d199-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="8d199-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8d199-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8d199-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8d199-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8d199-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8d199-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8d199-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8d199-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="8d199-107">\<tracking></span></span>  
<span data-ttu-id="8d199-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8d199-108">\<trackingProfile></span></span>  
<span data-ttu-id="8d199-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="8d199-109">\<workflow></span></span>  
<span data-ttu-id="8d199-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="8d199-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="8d199-111">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="8d199-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d199-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d199-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d199-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8d199-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8d199-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d199-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d199-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="8d199-115">Attributes</span></span>  
  
|<span data-ttu-id="8d199-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="8d199-116">Attribute</span></span>|<span data-ttu-id="8d199-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d199-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d199-118">activityName</span><span class="sxs-lookup"><span data-stu-id="8d199-118">activityName</span></span>|<span data-ttu-id="8d199-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="8d199-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="8d199-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="8d199-120">childActivityName</span></span>|<span data-ttu-id="8d199-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="8d199-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d199-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d199-122">Child Elements</span></span>  
 <span data-ttu-id="8d199-123">Keine</span><span class="sxs-lookup"><span data-stu-id="8d199-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d199-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d199-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8d199-125">Element</span><span class="sxs-lookup"><span data-stu-id="8d199-125">Element</span></span>|<span data-ttu-id="8d199-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d199-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d199-127">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="8d199-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="8d199-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="8d199-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d199-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d199-129">See Also</span></span>  
 <span data-ttu-id="8d199-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8d199-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="8d199-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8d199-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="8d199-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8d199-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8d199-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8d199-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

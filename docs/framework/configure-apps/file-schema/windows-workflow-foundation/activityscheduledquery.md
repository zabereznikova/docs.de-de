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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 779ac3995d4d5fb1b63de6ae6b9db7103691d6f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="72379-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="72379-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="72379-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="72379-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="72379-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="72379-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="72379-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="72379-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="72379-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="72379-106">\<system.serviceModel></span></span>  
<span data-ttu-id="72379-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="72379-107">\<tracking></span></span>  
<span data-ttu-id="72379-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="72379-108">\<trackingProfile></span></span>  
<span data-ttu-id="72379-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="72379-109">\<workflow></span></span>  
<span data-ttu-id="72379-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="72379-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="72379-111">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="72379-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72379-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="72379-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72379-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72379-113">Attributes and Elements</span></span>  
 <span data-ttu-id="72379-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72379-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72379-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="72379-115">Attributes</span></span>  
  
|<span data-ttu-id="72379-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="72379-116">Attribute</span></span>|<span data-ttu-id="72379-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72379-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72379-118">activityName</span><span class="sxs-lookup"><span data-stu-id="72379-118">activityName</span></span>|<span data-ttu-id="72379-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="72379-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="72379-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="72379-120">childActivityName</span></span>|<span data-ttu-id="72379-121">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="72379-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72379-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72379-122">Child Elements</span></span>  
 <span data-ttu-id="72379-123">Keine</span><span class="sxs-lookup"><span data-stu-id="72379-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72379-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72379-124">Parent Elements</span></span>  
  
|<span data-ttu-id="72379-125">Element</span><span class="sxs-lookup"><span data-stu-id="72379-125">Element</span></span>|<span data-ttu-id="72379-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72379-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72379-127">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="72379-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="72379-128">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="72379-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72379-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72379-129">See Also</span></span>  
 <span data-ttu-id="72379-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="72379-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="72379-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="72379-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="72379-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="72379-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="72379-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="72379-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

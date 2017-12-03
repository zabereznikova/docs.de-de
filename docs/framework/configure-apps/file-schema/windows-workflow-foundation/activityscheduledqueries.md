---
title: '&lt;activityScheduledQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d860474c4a638a347f85c07862c330f58cc30c09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="deb1a-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="deb1a-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="deb1a-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="deb1a-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="deb1a-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="deb1a-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="deb1a-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="deb1a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="deb1a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="deb1a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="deb1a-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="deb1a-107">\<tracking></span></span>  
<span data-ttu-id="deb1a-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="deb1a-108">\<trackingProfile></span></span>  
<span data-ttu-id="deb1a-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="deb1a-109">\<workflow></span></span>  
<span data-ttu-id="deb1a-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="deb1a-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb1a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="deb1a-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="deb1a-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="deb1a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="deb1a-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="deb1a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="deb1a-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="deb1a-114">Attributes</span></span>  
 <span data-ttu-id="deb1a-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="deb1a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="deb1a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="deb1a-116">Child Elements</span></span>  
  
|<span data-ttu-id="deb1a-117">Element</span><span class="sxs-lookup"><span data-stu-id="deb1a-117">Element</span></span>|<span data-ttu-id="deb1a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deb1a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="deb1a-119">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="deb1a-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="deb1a-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="deb1a-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="deb1a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="deb1a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="deb1a-122">Element</span><span class="sxs-lookup"><span data-stu-id="deb1a-122">Element</span></span>|<span data-ttu-id="deb1a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deb1a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="deb1a-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="deb1a-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="deb1a-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="deb1a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="deb1a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deb1a-126">See Also</span></span>  
 <span data-ttu-id="deb1a-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="deb1a-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="deb1a-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="deb1a-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="deb1a-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="deb1a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="deb1a-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="deb1a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;activityScheduledQueries&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fc263f0d70e7c1016bab819fb157dde6fad66d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="c0c27-102">&lt;activityScheduledQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="c0c27-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="c0c27-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c0c27-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c0c27-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c0c27-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c0c27-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c0c27-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="c0c27-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c0c27-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c0c27-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="c0c27-107">\<tracking></span></span>  
<span data-ttu-id="c0c27-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c0c27-108">\<trackingProfile></span></span>  
<span data-ttu-id="c0c27-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="c0c27-109">\<workflow></span></span>  
<span data-ttu-id="c0c27-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="c0c27-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c27-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0c27-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0c27-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c0c27-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c0c27-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0c27-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0c27-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0c27-114">Attributes</span></span>  
 <span data-ttu-id="c0c27-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="c0c27-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0c27-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0c27-116">Child Elements</span></span>  
  
|<span data-ttu-id="c0c27-117">Element</span><span class="sxs-lookup"><span data-stu-id="c0c27-117">Element</span></span>|<span data-ttu-id="c0c27-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0c27-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c27-119">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="c0c27-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="c0c27-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c0c27-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0c27-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c0c27-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c0c27-122">Element</span><span class="sxs-lookup"><span data-stu-id="c0c27-122">Element</span></span>|<span data-ttu-id="c0c27-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0c27-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c27-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="c0c27-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c0c27-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c0c27-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0c27-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0c27-126">See Also</span></span>  
 <span data-ttu-id="c0c27-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="c0c27-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="c0c27-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c0c27-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="c0c27-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c0c27-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c0c27-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c0c27-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

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
ms.workload: dotnet
ms.openlocfilehash: 5a857a86d45226e3dd3805a900612f55078c0bf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="8476f-102">&lt;activityScheduledQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="8476f-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="8476f-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="8476f-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8476f-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="8476f-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8476f-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8476f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="8476f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8476f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8476f-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="8476f-107">\<tracking></span></span>  
<span data-ttu-id="8476f-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8476f-108">\<trackingProfile></span></span>  
<span data-ttu-id="8476f-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="8476f-109">\<workflow></span></span>  
<span data-ttu-id="8476f-110">\<ActivityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="8476f-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8476f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="8476f-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8476f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8476f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8476f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8476f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8476f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="8476f-114">Attributes</span></span>  
 <span data-ttu-id="8476f-115">Keine</span><span class="sxs-lookup"><span data-stu-id="8476f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8476f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8476f-116">Child Elements</span></span>  
  
|<span data-ttu-id="8476f-117">Element</span><span class="sxs-lookup"><span data-stu-id="8476f-117">Element</span></span>|<span data-ttu-id="8476f-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8476f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8476f-119">\<ActivityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="8476f-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="8476f-120">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="8476f-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8476f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8476f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8476f-122">Element</span><span class="sxs-lookup"><span data-stu-id="8476f-122">Element</span></span>|<span data-ttu-id="8476f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8476f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8476f-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="8476f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8476f-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8476f-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8476f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8476f-126">See Also</span></span>  
 <span data-ttu-id="8476f-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="8476f-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="8476f-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="8476f-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="8476f-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="8476f-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8476f-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="8476f-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

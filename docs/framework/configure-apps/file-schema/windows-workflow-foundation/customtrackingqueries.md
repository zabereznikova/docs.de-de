---
title: '&lt;customTrackingQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 241684a3a2344d6eb7f3b34c81c581b0ec5130f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="a18a8-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a18a8-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="a18a8-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="a18a8-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a18a8-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="a18a8-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="a18a8-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a18a8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a18a8-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a18a8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a18a8-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="a18a8-107">\<tracking></span></span>  
<span data-ttu-id="a18a8-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a18a8-108">\<trackingProfile></span></span>  
<span data-ttu-id="a18a8-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a18a8-109">\<workflow></span></span>  
<span data-ttu-id="a18a8-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="a18a8-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a18a8-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a18a8-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a18a8-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a18a8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a18a8-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a18a8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a18a8-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a18a8-114">Attributes</span></span>  
 <span data-ttu-id="a18a8-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="a18a8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a18a8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a18a8-116">Child Elements</span></span>  
  
|<span data-ttu-id="a18a8-117">Element</span><span class="sxs-lookup"><span data-stu-id="a18a8-117">Element</span></span>|<span data-ttu-id="a18a8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a18a8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a18a8-119">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="a18a8-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="a18a8-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="a18a8-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a18a8-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a18a8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a18a8-122">Element</span><span class="sxs-lookup"><span data-stu-id="a18a8-122">Element</span></span>|<span data-ttu-id="a18a8-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a18a8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a18a8-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="a18a8-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a18a8-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow identifizierte enthält die **ActivityDefinitionId** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a18a8-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a18a8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a18a8-126">See Also</span></span>  
 <span data-ttu-id="a18a8-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a18a8-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a18a8-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a18a8-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a18a8-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="a18a8-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a18a8-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="a18a8-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

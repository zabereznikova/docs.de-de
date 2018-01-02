---
title: '&lt;customTrackingQueries&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a64a155f435fb61c19a50f1b047c7dd28b603716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="b5f52-102">&lt;customTrackingQueries&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="b5f52-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="b5f52-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="b5f52-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="b5f52-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="b5f52-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="b5f52-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b5f52-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="b5f52-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b5f52-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b5f52-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="b5f52-107">\<tracking></span></span>  
<span data-ttu-id="b5f52-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b5f52-108">\<trackingProfile></span></span>  
<span data-ttu-id="b5f52-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b5f52-109">\<workflow></span></span>  
<span data-ttu-id="b5f52-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="b5f52-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5f52-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5f52-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5f52-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5f52-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b5f52-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5f52-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5f52-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5f52-114">Attributes</span></span>  
 <span data-ttu-id="b5f52-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b5f52-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5f52-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5f52-116">Child Elements</span></span>  
  
|<span data-ttu-id="b5f52-117">Element</span><span class="sxs-lookup"><span data-stu-id="b5f52-117">Element</span></span>|<span data-ttu-id="b5f52-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5f52-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5f52-119">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="b5f52-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="b5f52-120">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="b5f52-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5f52-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5f52-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b5f52-122">Element</span><span class="sxs-lookup"><span data-stu-id="b5f52-122">Element</span></span>|<span data-ttu-id="b5f52-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5f52-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5f52-124">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="b5f52-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b5f52-125">Ein Konfigurationselement, das alle Abfragen für einen bestimmten Workflow enthält, der durch die `activityDefinitionId`-Eigenschaft identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b5f52-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5f52-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5f52-126">See Also</span></span>  
 <span data-ttu-id="b5f52-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b5f52-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b5f52-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b5f52-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b5f52-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="b5f52-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b5f52-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="b5f52-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

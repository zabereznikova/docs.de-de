---
title: '&lt;customTrackingQuery&gt; von WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27637abceb23a54e784afbcc2e0517db51542b53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="3fd53-102">&lt;customTrackingQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="3fd53-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="3fd53-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3fd53-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="3fd53-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3fd53-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="3fd53-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3fd53-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="3fd53-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3fd53-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3fd53-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3fd53-107">\<tracking></span></span>  
<span data-ttu-id="3fd53-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3fd53-108">\<trackingProfile></span></span>  
<span data-ttu-id="3fd53-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3fd53-109">\<workflow></span></span>  
<span data-ttu-id="3fd53-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="3fd53-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="3fd53-111">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="3fd53-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd53-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fd53-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fd53-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3fd53-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3fd53-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3fd53-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fd53-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="3fd53-115">Attributes</span></span>  
  
|<span data-ttu-id="3fd53-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="3fd53-116">Attribute</span></span>|<span data-ttu-id="3fd53-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fd53-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fd53-118">activityName</span><span class="sxs-lookup"><span data-stu-id="3fd53-118">activityName</span></span>|<span data-ttu-id="3fd53-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="3fd53-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="3fd53-120">Name</span><span class="sxs-lookup"><span data-stu-id="3fd53-120">name</span></span>|<span data-ttu-id="3fd53-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="3fd53-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fd53-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fd53-122">Child Elements</span></span>  
 <span data-ttu-id="3fd53-123">Keine</span><span class="sxs-lookup"><span data-stu-id="3fd53-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fd53-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fd53-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3fd53-125">Element</span><span class="sxs-lookup"><span data-stu-id="3fd53-125">Element</span></span>|<span data-ttu-id="3fd53-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fd53-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fd53-127">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="3fd53-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="3fd53-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3fd53-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fd53-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fd53-129">See Also</span></span>  
 <span data-ttu-id="3fd53-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3fd53-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="3fd53-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3fd53-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3fd53-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3fd53-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3fd53-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3fd53-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

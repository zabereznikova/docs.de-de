---
title: '&lt;customTrackingQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d4427ad1b45ceade29b8859d30eba746a70a27d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="60314-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="60314-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="60314-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="60314-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="60314-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="60314-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="60314-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="60314-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="60314-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="60314-106">\<system.serviceModel></span></span>  
<span data-ttu-id="60314-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="60314-107">\<tracking></span></span>  
<span data-ttu-id="60314-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="60314-108">\<trackingProfile></span></span>  
<span data-ttu-id="60314-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="60314-109">\<workflow></span></span>  
<span data-ttu-id="60314-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="60314-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="60314-111">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="60314-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60314-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="60314-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60314-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60314-113">Attributes and Elements</span></span>  
 <span data-ttu-id="60314-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60314-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60314-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="60314-115">Attributes</span></span>  
  
|<span data-ttu-id="60314-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="60314-116">Attribute</span></span>|<span data-ttu-id="60314-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60314-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60314-118">activityName</span><span class="sxs-lookup"><span data-stu-id="60314-118">activityName</span></span>|<span data-ttu-id="60314-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="60314-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="60314-120">Name</span><span class="sxs-lookup"><span data-stu-id="60314-120">name</span></span>|<span data-ttu-id="60314-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="60314-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60314-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60314-122">Child Elements</span></span>  
 <span data-ttu-id="60314-123">Keine</span><span class="sxs-lookup"><span data-stu-id="60314-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60314-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60314-124">Parent Elements</span></span>  
  
|<span data-ttu-id="60314-125">Element</span><span class="sxs-lookup"><span data-stu-id="60314-125">Element</span></span>|<span data-ttu-id="60314-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60314-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60314-127">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="60314-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="60314-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="60314-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60314-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60314-129">See Also</span></span>  
 <span data-ttu-id="60314-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60314-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="60314-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="60314-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="60314-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="60314-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="60314-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="60314-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

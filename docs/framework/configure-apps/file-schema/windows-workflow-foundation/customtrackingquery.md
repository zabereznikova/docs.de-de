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
ms.openlocfilehash: 908c340167d50d4d16e0eeff7cc2e01290b55e7a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="87991-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="87991-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="87991-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="87991-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="87991-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="87991-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="87991-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="87991-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="87991-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="87991-106">\<system.serviceModel></span></span>  
<span data-ttu-id="87991-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="87991-107">\<tracking></span></span>  
<span data-ttu-id="87991-108">\<TrackingProfile ></span><span class="sxs-lookup"><span data-stu-id="87991-108">\<trackingProfile></span></span>  
<span data-ttu-id="87991-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="87991-109">\<workflow></span></span>  
<span data-ttu-id="87991-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="87991-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="87991-111">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="87991-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87991-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="87991-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87991-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87991-113">Attributes and Elements</span></span>  
 <span data-ttu-id="87991-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87991-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87991-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="87991-115">Attributes</span></span>  
  
|<span data-ttu-id="87991-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="87991-116">Attribute</span></span>|<span data-ttu-id="87991-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87991-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87991-118">activityName</span><span class="sxs-lookup"><span data-stu-id="87991-118">activityName</span></span>|<span data-ttu-id="87991-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="87991-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="87991-120">Name</span><span class="sxs-lookup"><span data-stu-id="87991-120">name</span></span>|<span data-ttu-id="87991-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="87991-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87991-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87991-122">Child Elements</span></span>  
 <span data-ttu-id="87991-123">Keine</span><span class="sxs-lookup"><span data-stu-id="87991-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87991-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87991-124">Parent Elements</span></span>  
  
|<span data-ttu-id="87991-125">Element</span><span class="sxs-lookup"><span data-stu-id="87991-125">Element</span></span>|<span data-ttu-id="87991-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87991-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87991-127">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="87991-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="87991-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="87991-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87991-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87991-129">See Also</span></span>  
 <span data-ttu-id="87991-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="87991-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="87991-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="87991-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="87991-132">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="87991-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="87991-133">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="87991-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

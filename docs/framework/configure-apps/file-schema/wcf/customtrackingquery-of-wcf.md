---
title: '&lt;customTrackingQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: ed29ff039cd7fd4eb0acccea1b0adf8995c3e1f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747033"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="92202-102">&lt;customTrackingQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="92202-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="92202-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="92202-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="92202-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="92202-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="92202-105">Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="92202-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="92202-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="92202-106">\<system.serviceModel></span></span>  
<span data-ttu-id="92202-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="92202-107">\<tracking></span></span>  
<span data-ttu-id="92202-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="92202-108">\<trackingProfile></span></span>  
<span data-ttu-id="92202-109">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="92202-109">\<workflow></span></span>  
<span data-ttu-id="92202-110">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="92202-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="92202-111">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="92202-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92202-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="92202-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92202-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92202-113">Attributes and Elements</span></span>  
 <span data-ttu-id="92202-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92202-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92202-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="92202-115">Attributes</span></span>  
  
|<span data-ttu-id="92202-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="92202-116">Attribute</span></span>|<span data-ttu-id="92202-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92202-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92202-118">activityName</span><span class="sxs-lookup"><span data-stu-id="92202-118">activityName</span></span>|<span data-ttu-id="92202-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="92202-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="92202-120">Name</span><span class="sxs-lookup"><span data-stu-id="92202-120">name</span></span>|<span data-ttu-id="92202-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="92202-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92202-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92202-122">Child Elements</span></span>  
 <span data-ttu-id="92202-123">Keine</span><span class="sxs-lookup"><span data-stu-id="92202-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92202-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92202-124">Parent Elements</span></span>  
  
|<span data-ttu-id="92202-125">Element</span><span class="sxs-lookup"><span data-stu-id="92202-125">Element</span></span>|<span data-ttu-id="92202-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92202-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92202-127">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="92202-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="92202-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="92202-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92202-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92202-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="92202-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="92202-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="92202-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="92202-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

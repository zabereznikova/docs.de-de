---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9ee5a4a25d379eafb936098597df1ec61ff09f0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725856"
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="ac29d-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ac29d-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="ac29d-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="ac29d-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ac29d-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="ac29d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ac29d-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ac29d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ac29d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ac29d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ac29d-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ac29d-107">\<tracking></span></span>  
<span data-ttu-id="ac29d-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ac29d-108">\<trackingProfile></span></span>  
<span data-ttu-id="ac29d-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ac29d-109">\<workflow></span></span>  
<span data-ttu-id="ac29d-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ac29d-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="ac29d-111">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac29d-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac29d-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac29d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac29d-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac29d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ac29d-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac29d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac29d-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac29d-115">Attributes</span></span>  
  
|<span data-ttu-id="ac29d-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac29d-116">Attribute</span></span>|<span data-ttu-id="ac29d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac29d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac29d-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ac29d-118">activityName</span></span>|<span data-ttu-id="ac29d-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="ac29d-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="ac29d-120">Name</span><span class="sxs-lookup"><span data-stu-id="ac29d-120">name</span></span>|<span data-ttu-id="ac29d-121">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="ac29d-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac29d-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac29d-122">Child Elements</span></span>  
 <span data-ttu-id="ac29d-123">Keine</span><span class="sxs-lookup"><span data-stu-id="ac29d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac29d-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac29d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ac29d-125">Element</span><span class="sxs-lookup"><span data-stu-id="ac29d-125">Element</span></span>|<span data-ttu-id="ac29d-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac29d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac29d-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac29d-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ac29d-128">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="ac29d-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac29d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac29d-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ac29d-130">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="ac29d-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ac29d-131">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ac29d-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

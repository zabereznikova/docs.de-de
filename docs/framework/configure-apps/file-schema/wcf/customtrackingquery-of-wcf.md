---
title: '&lt;customTrackingQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: e13064afbd9f5dbc8d7216eb384001e1e005785c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316232"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="3a1ee-102">&lt;customTrackingQuery&gt; von WCF</span><span class="sxs-lookup"><span data-stu-id="3a1ee-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="3a1ee-103">Stellt eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="3a1ee-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="3a1ee-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3a1ee-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3a1ee-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a1ee-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3a1ee-107">\<Nachverfolgen von ></span><span class="sxs-lookup"><span data-stu-id="3a1ee-107">\<tracking></span></span>  
<span data-ttu-id="3a1ee-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="3a1ee-108">\<profiles></span></span>  
<span data-ttu-id="3a1ee-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3a1ee-109">\<trackingProfile></span></span>  
<span data-ttu-id="3a1ee-110">\<Workflow ></span><span class="sxs-lookup"><span data-stu-id="3a1ee-110">\<workflow></span></span>  
<span data-ttu-id="3a1ee-111">\<CustomTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="3a1ee-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="3a1ee-112">\<CustomTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="3a1ee-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1ee-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a1ee-113">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a1ee-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a1ee-114">Attributes and elements</span></span>  

<span data-ttu-id="3a1ee-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a1ee-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a1ee-116">Attributes</span></span>  
  
|<span data-ttu-id="3a1ee-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a1ee-117">Attribute</span></span>|<span data-ttu-id="3a1ee-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a1ee-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="3a1ee-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="3a1ee-120">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a1ee-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a1ee-121">Child elements</span></span>

<span data-ttu-id="3a1ee-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3a1ee-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3a1ee-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a1ee-123">Parent elements</span></span>

|<span data-ttu-id="3a1ee-124">Element</span><span class="sxs-lookup"><span data-stu-id="3a1ee-124">Element</span></span>|<span data-ttu-id="3a1ee-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a1ee-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a1ee-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="3a1ee-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="3a1ee-127">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="3a1ee-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a1ee-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a1ee-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="3a1ee-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a1ee-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="3a1ee-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: <customTrackingQuery> von WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279486"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="905b6-102">\<CustomTrackingQuery > von WCF</span><span class="sxs-lookup"><span data-stu-id="905b6-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="905b6-103">Stellt eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="905b6-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="905b6-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="905b6-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="905b6-105">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="905b6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="905b6-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="905b6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="905b6-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="905b6-107">\<tracking></span></span>  
<span data-ttu-id="905b6-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="905b6-108">\<profiles></span></span>  
<span data-ttu-id="905b6-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="905b6-109">\<trackingProfile></span></span>  
<span data-ttu-id="905b6-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="905b6-110">\<workflow></span></span>  
<span data-ttu-id="905b6-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="905b6-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="905b6-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="905b6-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905b6-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="905b6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="905b6-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="905b6-114">Attributes and elements</span></span>  

<span data-ttu-id="905b6-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="905b6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="905b6-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="905b6-116">Attributes</span></span>  
  
|<span data-ttu-id="905b6-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="905b6-117">Attribute</span></span>|<span data-ttu-id="905b6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="905b6-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="905b6-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="905b6-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="905b6-120">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="905b6-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="905b6-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="905b6-121">Child elements</span></span>

<span data-ttu-id="905b6-122">Keine</span><span class="sxs-lookup"><span data-stu-id="905b6-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="905b6-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="905b6-123">Parent elements</span></span>

|<span data-ttu-id="905b6-124">Element</span><span class="sxs-lookup"><span data-stu-id="905b6-124">Element</span></span>|<span data-ttu-id="905b6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="905b6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="905b6-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="905b6-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="905b6-127">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="905b6-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="905b6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="905b6-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="905b6-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="905b6-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="905b6-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="905b6-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

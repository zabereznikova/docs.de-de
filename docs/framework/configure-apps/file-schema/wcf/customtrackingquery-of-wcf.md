---
title: <customTrackingQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919362"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="4b85b-102">\<CustomTrackingQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="4b85b-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="4b85b-103">Stellt eine Abfrage dar, die verwendet wird, um Ereignisse zu verfolgen, die Sie in den Code Aktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="4b85b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="4b85b-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="4b85b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="4b85b-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4b85b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4b85b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b85b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4b85b-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="4b85b-107">\<tracking></span></span>  
<span data-ttu-id="4b85b-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="4b85b-108">\<profiles></span></span>  
<span data-ttu-id="4b85b-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4b85b-109">\<trackingProfile></span></span>  
<span data-ttu-id="4b85b-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4b85b-110">\<workflow></span></span>  
<span data-ttu-id="4b85b-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="4b85b-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="4b85b-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="4b85b-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b85b-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b85b-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b85b-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b85b-114">Attributes and elements</span></span>  

<span data-ttu-id="4b85b-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b85b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b85b-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b85b-116">Attributes</span></span>  
  
|<span data-ttu-id="4b85b-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b85b-117">Attribute</span></span>|<span data-ttu-id="4b85b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b85b-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="4b85b-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="4b85b-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="4b85b-120">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="4b85b-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b85b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b85b-121">Child elements</span></span>

<span data-ttu-id="4b85b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4b85b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b85b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b85b-123">Parent elements</span></span>

|<span data-ttu-id="4b85b-124">Element</span><span class="sxs-lookup"><span data-stu-id="4b85b-124">Element</span></span>|<span data-ttu-id="4b85b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b85b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b85b-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="4b85b-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="4b85b-127">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="4b85b-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="4b85b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b85b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4b85b-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="4b85b-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4b85b-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="4b85b-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

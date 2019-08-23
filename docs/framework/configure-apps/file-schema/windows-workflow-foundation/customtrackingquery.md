---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9605f5d050baf046ff3c549c19191934299a65e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945751"
---
# <a name="customtrackingquery"></a><span data-ttu-id="63868-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="63868-101">\<customTrackingQuery></span></span>
<span data-ttu-id="63868-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="63868-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="63868-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer benutzerdefinierte Nachverfolgungsdatensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="63868-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="63868-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="63868-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="63868-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="63868-105">\<system.serviceModel></span></span>  
<span data-ttu-id="63868-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="63868-106">\<tracking></span></span>  
<span data-ttu-id="63868-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="63868-107">\<trackingProfile></span></span>  
<span data-ttu-id="63868-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="63868-108">\<workflow></span></span>  
<span data-ttu-id="63868-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="63868-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="63868-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="63868-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63868-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="63868-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63868-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="63868-112">Attributes and Elements</span></span>  
 <span data-ttu-id="63868-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="63868-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63868-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="63868-114">Attributes</span></span>  
  
|<span data-ttu-id="63868-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="63868-115">Attribute</span></span>|<span data-ttu-id="63868-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63868-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63868-117">activityName</span><span class="sxs-lookup"><span data-stu-id="63868-117">activityName</span></span>|<span data-ttu-id="63868-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Nachverfolgungsdatensatz generiert hat.</span><span class="sxs-lookup"><span data-stu-id="63868-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="63868-119">Name</span><span class="sxs-lookup"><span data-stu-id="63868-119">name</span></span>|<span data-ttu-id="63868-120">Eine Zeichenfolge, die den Namen des ausgegebenen benutzerdefinierten Nachverfolgungsdatensatzes angibt.</span><span class="sxs-lookup"><span data-stu-id="63868-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63868-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="63868-121">Child Elements</span></span>  
 <span data-ttu-id="63868-122">Keine</span><span class="sxs-lookup"><span data-stu-id="63868-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63868-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="63868-123">Parent Elements</span></span>  
  
|<span data-ttu-id="63868-124">Element</span><span class="sxs-lookup"><span data-stu-id="63868-124">Element</span></span>|<span data-ttu-id="63868-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63868-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63868-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="63868-126">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="63868-127">Eine Abfrage, die verwendet wird, um Ereignisse nachzuverfolgen, die Sie in den Codeaktivitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="63868-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63868-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63868-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="63868-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="63868-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="63868-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="63868-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

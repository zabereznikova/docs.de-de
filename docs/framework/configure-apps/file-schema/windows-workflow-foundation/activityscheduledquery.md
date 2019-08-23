---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945503"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="c7b12-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c7b12-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="c7b12-102">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c7b12-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c7b12-103">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c7b12-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c7b12-104">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c7b12-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c7b12-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c7b12-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c7b12-106">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="c7b12-106">\<tracking></span></span>  
<span data-ttu-id="c7b12-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c7b12-107">\<trackingProfile></span></span>  
<span data-ttu-id="c7b12-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c7b12-108">\<workflow></span></span>  
<span data-ttu-id="c7b12-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="c7b12-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="c7b12-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c7b12-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b12-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7b12-111">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7b12-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7b12-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c7b12-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7b12-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7b12-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="c7b12-114">Attributes</span></span>  
  
|<span data-ttu-id="c7b12-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="c7b12-115">Attribute</span></span>|<span data-ttu-id="c7b12-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7b12-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7b12-117">activityName</span><span class="sxs-lookup"><span data-stu-id="c7b12-117">activityName</span></span>|<span data-ttu-id="c7b12-118">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="c7b12-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="c7b12-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="c7b12-119">childActivityName</span></span>|<span data-ttu-id="c7b12-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7b12-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7b12-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7b12-121">Child Elements</span></span>  
 <span data-ttu-id="c7b12-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c7b12-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7b12-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7b12-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c7b12-124">Element</span><span class="sxs-lookup"><span data-stu-id="c7b12-124">Element</span></span>|<span data-ttu-id="c7b12-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7b12-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7b12-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c7b12-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="c7b12-127">Eine Abfrage, die verwendet wird, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="c7b12-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7b12-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7b12-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c7b12-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="c7b12-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c7b12-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="c7b12-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)

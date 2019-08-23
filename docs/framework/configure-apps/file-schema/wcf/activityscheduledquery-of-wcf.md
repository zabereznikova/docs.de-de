---
title: <activityScheduledQuery>von WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 7787ada68210ff832ff3fd1ec93c9d346e4d2eaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926928"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="56b22-102">\<ActivityScheduledQuery-> von WCF</span><span class="sxs-lookup"><span data-stu-id="56b22-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="56b22-103">Stellt eine Auflistung von Abfragen dar, die verwendet werden, um eine Aktivität zu verfolgen, deren Ausführung von einer übergeordneten Aktivität geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="56b22-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="56b22-104">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer die Datensätze der geplanten Aktivität abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="56b22-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="56b22-105">Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="56b22-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="56b22-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="56b22-106">\<system.serviceModel></span></span>  
<span data-ttu-id="56b22-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="56b22-107">\<tracking></span></span>  
<span data-ttu-id="56b22-108">\<Profile ></span><span class="sxs-lookup"><span data-stu-id="56b22-108">\<profiles></span></span>  
<span data-ttu-id="56b22-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="56b22-109">\<trackingProfile></span></span>  
<span data-ttu-id="56b22-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="56b22-110">\<workflow></span></span>  
<span data-ttu-id="56b22-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="56b22-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="56b22-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="56b22-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56b22-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="56b22-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56b22-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56b22-114">Attributes and elements</span></span>  

<span data-ttu-id="56b22-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56b22-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56b22-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="56b22-116">Attributes</span></span>  
  
|<span data-ttu-id="56b22-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="56b22-117">Attribute</span></span>|<span data-ttu-id="56b22-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56b22-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="56b22-119">Eine Zeichenfolge, die den Namen der Aktivität angibt, die den Abbruch anfordert.</span><span class="sxs-lookup"><span data-stu-id="56b22-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="56b22-120">Eine Zeichenfolge, die den Namen der untergeordneten Aktivität angibt, für die der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="56b22-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56b22-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56b22-121">Child elements</span></span>

<span data-ttu-id="56b22-122">Keine</span><span class="sxs-lookup"><span data-stu-id="56b22-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="56b22-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56b22-123">Parent elements</span></span>  
  
|<span data-ttu-id="56b22-124">Element</span><span class="sxs-lookup"><span data-stu-id="56b22-124">Element</span></span>|<span data-ttu-id="56b22-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56b22-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56b22-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="56b22-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="56b22-127">Eine Auflistung von Abfragen, die verwendet werden, um eine Aktivität zu verfolgen, die für die Ausführung durch eine übergeordnete Aktivität geplant ist.</span><span class="sxs-lookup"><span data-stu-id="56b22-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56b22-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56b22-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="56b22-129">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="56b22-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="56b22-130">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="56b22-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
